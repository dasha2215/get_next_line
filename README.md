# get_next_line

## Overview

The `get_next_line` project is a custom implementation of a function that reads a line from a file descriptor. This project demonstrates the use of static variables and provides a convenient function to add to your C programming toolkit.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Usage](#usage)
- [Functions](#functions)
- [License](#license)

## Introduction

The `get_next_line` function is designed to read a line from a file descriptor. This function handles multiple file descriptors, static variables, and efficient memory management. It can be used to read from both files and standard input, returning one line at a time.

## Features

- Implementation of `get_next_line()` function.
- Efficient handling of file descriptors and static variables.
- Comprehensive Makefile for building the library.
- Adherence to strict coding standards and norms.

## Usage

To use the `get_next_line` function, include the header file and call `get_next_line` as shown in the example below. Make sure to compile all the necessary source files together.

1. Include the `get_next_line.h` header in your project.

2. Use the following command to compile your project with the `get_next_line` function:

   ```sh
   gcc -o my_program my_program.c get_next_line.c get_next_line_utils.c
   ```

3. Example usage:

```c
Copy code
#include "get_next_line.h"
#include <fcntl.h>
#include <stdio.h>

int main() {
    int fd = open("testfile.txt", O_RDONLY);
    char *line;

    while ((line = get_next_line(fd)) != NULL) {
        printf("%s", line);
        free(line);
    }

    close(fd);
    return 0;
}
```

## Functions

### Mandatory Functions

The `get_next_line` function has the following prototype:

```c
  char *get_next_line(int fd);
```

#### Parameters

__fd :__ The file descriptor to read from.

#### Return value
Returns the line read from the file descriptor. Returns NULL if there is nothing more to read or if an error occurred.

### Bonus Functions
The bonus functions extend the get_next_line function to handle multiple file descriptors simultaneously using only one static variable. The prototype is as follows:

```c
char *get_next_line_bonus(int fd);
```

#### Parameters

__fd :__ The file descriptor to read from.

#### Return value

Returns the line read from the file descriptor. Returns NULL if there is nothing more to read or if an error occurred.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
