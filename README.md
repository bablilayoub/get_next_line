# Get Next Line

## Summary

This project involves programming a function, `get_next_line`, that returns a line read from a file descriptor. The project not only adds a convenient function to your collection but also introduces the concept of static variables in C programming.

## Contents

- [I. Goals](#i-goals)
- [II. Common Instructions](#ii-common-instructions)
- [III. Mandatory Part](#iii-mandatory-part)
- [IV. Bonus Part](#iv-bonus-part)
- [V. Submission and Peer-Evaluation](#v-submission-and-peer-evaluation)

## I. Goals

This project will not only allow you to add a very convenient function to your collection but will also make you learn a highly interesting new concept in C programming: static variables.

## II. Common Instructions

- Your project must be written in C.
- Adhere to the Norm guidelines, including bonus files/functions.
- Functions should not quit unexpectedly (e.g., segmentation fault, bus error).
- Properly free all heap-allocated memory to avoid memory leaks.
- Submit a Makefile to compile source files with specific flags.
- Include rules in the Makefile: `$(NAME)`, `all`, `clean`, `fclean`, and `re`.
- For bonus submission, add a `bonus` rule to the Makefile.
- Encourage creating test programs for project validation.
- Submit your work to the assigned Git repository.

## III. Mandatory Part

### Function: get_next_line

#### Prototype
```c
char *get_next_line(int fd);
```
#### Turn in files
- `get_next_line.c`
- `get_next_line_utils.c`
- `get_next_line.h`

#### Parameters
- `fd`: The file descriptor to read from

#### Return value
- Read line: correct behavior
- `NULL`: There is nothing else to read, or an error occurred

#### External functions
`read`, `malloc`, `free`

#### Description
Write a function that returns a line read from a file descriptor. Repeated calls to `get_next_line()` should let you read a text file, one line at a time. The function should return the line that was read, or `NULL` if there is nothing else to read or if an error occurred. The returned line should include the terminating `\n` character, except at the end of the file.

- Header file `get_next_line.h` must contain at least the prototype of the `get_next_line()` function.
- Add helper functions in the `get_next_line_utils.c` file.

#### Additional Requirements
- Define the buffer size for `read()` using the `-D BUFFER_SIZE=n` compiler option.
- The buffer size value will be modified by peer-evaluators and the Moulinette for testing.
- Handle undefined behavior if the file pointed to by the file descriptor changed since the last call without reaching the end of the file.
- Handle undefined behavior when reading a binary file.

## IV. Bonus Part

#### Additional Requirements
- Develop `get_next_line()` using only one static variable.
- Manage multiple file descriptors simultaneously.
- Append the `_bonus.[c\h]` suffix to the bonus part files.

#### Note
The bonus part will only be assessed if the mandatory part is PERFECT. Perfect means the mandatory part has been integrally done and works without malfunctioning.

## V. Submission and Peer-Evaluation

Turn in your assignment in your Git repository. Only the work inside your repository will be evaluated during the defense. Double-check file names for correctness.

When writing tests, consider diverse values for buffer size and line size. Remember that a file descriptor does not only point to regular files. Cross-check with peers and prepare a full set of diverse tests for defense. Once passed, consider adding your `get_next_line()` to your libft.
