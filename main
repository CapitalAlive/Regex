def print_test(*string, on_test=None):
    new_str = ""
    for element in string:
        new_str = new_str + " " + str(element)
    if on_test is True:
        print(new_str, flush=True)


def regex_function(regex, word, testing=True):
    regex, word = list(regex), list(word)
    if True:
        if not regex:
            return True
        elif not word:
            print_test("false 4", on_test=testing)
            return False

    if True:
        if regex[0] == "^":
            if regex[1] == "." and regex[2] in ["?", "*"]:
                regex.pop(0)
                regex.pop(1)
                regex.pop(2)
                word_iterations = range(len(word))
            else:
                word_iterations = range(1)
                regex.pop(0)
        else:
            word_iterations = range(len(word))

        default_regex, default_word = list(regex), list(word)

    for word_index in word_iterations:
        print_test("WORD LOOP", on_test=testing)
        regex, word = default_regex, default_word
        regex_index = -1
        for _ in regex:
            print_test("REGEX LOOP", on_test=testing)
            regex_index += 1
            print_test("regex:", regex[regex_index], "letter:", word[regex_index + word_index], on_test=testing)
            if regex_index < len(regex) - 1:
                # Checks for escaping character
                if regex[regex_index] != "\\":

                    if regex[regex_index + 1] == "?":
                        regex.pop(regex_index + 1)
                        # Check if the current regex matches with the current word:
                        if regex[regex_index] == word[regex_index + word_index]:
                            continue
                        elif regex[regex_index] == ".":
                            # Check if it is the last regex:
                            if regex_index == len(regex) - 1:
                                return True
                            if regex[regex_index + 1] == word[word_index + 1]:
                                continue
                            elif regex[regex_index + 1] == word[word_index]:
                                regex.pop(regex_index)
                        else:
                            print_test("there is a mistake here")
                            return True
                        pass
                    elif regex[regex_index + 1] == "*":
                        regex.pop(regex_index + 1)
                        # Check if the current regex matches with the current word:
                        if regex[regex_index] == word[regex_index + word_index]:
                            # if regex_index + word_index <
                            while regex[regex_index] == word[regex_index + word_index + 1]:
                                word.pop(regex_index + word_index)
                            continue
                        elif regex[regex_index] == ".":
                            # Check if it is the last regex:
                            if regex_index == len(regex) - 1:
                                return True
                            if regex[regex_index + 1] == word[word_index + 1]:
                                continue
                            elif regex[regex_index + 1] == word[word_index]:
                                regex.pop(regex_index)
                        else:
                            print_test("there is a mistake here")
                            return True
                        pass
                    elif regex[regex_index + 1] == "+":
                        regex.pop(regex_index + 1)
                        # Check if the current regex matches with the current word:
                        if regex[regex_index] in [word[regex_index + word_index], "."]:
                            # if regex_index + word_index <
                            print_test("testing 2", on_test=testing)
                            if regex[regex_index] == ".":
                                while len(word) - 1 > regex_index + word_index:
                                    if word[regex_index + word_index] == word[regex_index + word_index + 1]:
                                        word.pop(regex_index + word_index + 1)
                                    else:
                                        break
                            else:
                                while regex[regex_index] == word[regex_index + word_index + 1]:
                                    word.pop(regex_index + word_index)
                            print_test(word, on_test=testing)
                            # Check if it is the last regex:

                            if regex_index == len(regex) - 1:
                                return True
                            if regex[regex_index + 1] == word[word_index + 1]:
                                continue
                elif regex[regex_index] == "\\":
                    regex.pop(regex_index)
                if regex[regex_index] not in [word[word_index + regex_index], "."]:
                    print_test("end of line", on_test=testing)
                    if word_index + regex_index == len(word) - 1:
                        print_test("false 1", on_test=testing)
                        return False
                    break
                if regex_index < len(regex) - 1 and regex[regex_index + 1] == "$":
                    # Checks if current word and current regex match.
                    if regex[regex_index] in [word[regex_index + word_index], "."]:
                        # Checks if this is the last letter of the word
                        if regex_index + word_index == len(word) - 1:
                            return True
                    print_test("testing 1", on_test=testing)
            if regex_index == len(regex) - 1:
                print_test("last iteration of the loop")
                if regex[regex_index] in [word[word_index + regex_index], "."]:
                    print_test("lol")
                    return True
    print_test("false 2", on_test=testing)
    return False


if __name__ == "__main__":
    r, w = input().split("|")
    print(regex_function(r, w, testing=False))
