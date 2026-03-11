# ft_printf

A custom implementation of the C `printf` function, built as part of the [42 school](https://42.fr/) curriculum.

## Description

`ft_printf` is a simplified recreation of the standard C library function `printf`. It handles variadic arguments and supports a subset of format specifiers to produce formatted output to the standard output.

The project produces a static library (`libftprintf.a`) that can be linked into other C programs.

## Supported Format Specifiers

| Specifier | Description |
|-----------|-------------|
| `%c` | Print a single character |
| `%s` | Print a string |
| `%d` | Print a signed decimal integer |
| `%i` | Print a signed decimal integer |
| `%u` | Print an unsigned decimal integer |
| `%x` | Print a number in lowercase hexadecimal |
| `%X` | Print a number in uppercase hexadecimal |
| `%p` | Print a pointer address |
| `%%` | Print a literal `%` character |

## Build

Requires a C compiler (`cc`) and `make`.

```bash
# Build the library
make

# Remove object files
make clean

# Remove object files and the library
make fclean

# Rebuild from scratch
make re
```

## Usage

1. Build the library:
   ```bash
   make
   ```
2. Include the header and link the library when compiling your program:
   ```bash
   cc -Wall -Wextra -Werror main.c -L. -lftprintf -o my_program
   ```

### Example

```c
#include "ft_printf.h"

int main(void)
{
    ft_printf("Hello, %s!\n", "world");
    ft_printf("Dec: %d, Hex: %x, Ptr: %p\n", 42, 42, &main);
    return 0;
}
```

## Files

| File | Description |
|------|-------------|
| `ft_printf.c` | Core `ft_printf` and `ft_vprintf` implementation |
| `ft_putchar.c` | Character output |
| `ft_putstr.c` | String output |
| `ft_putnbr.c` | Signed integer output |
| `ft_putunsinged.c` | Unsigned integer output |
| `ft_puthex.c` | Lowercase hexadecimal output |
| `ft_putHEX.c` | Uppercase hexadecimal output |
| `ft_putaddr.c` | Pointer address output |
| `ft_printf.h` | Header file with function prototypes |
