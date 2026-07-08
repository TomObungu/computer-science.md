https://www.geeksforgeeks.org/c/format-specifiers-in-c/

https://cplusplus.com/reference/cstdio/printf/#google_vignette

https://learn.microsoft.com/en-us/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions?view=msvc-170

C strings that are written to `stdout` can have format specifiers that are replaced by the values specified in subsequent additional arugments and formatted as requested

The syntax for format specifiers is as follow

```

% [flags] [width] [.precision] [length] specifier

```

The specifier character at the end is the most significant component 

# Specifiers
`%d or %i`  - signed integers
`%u` - unsigned integers

## Unsigned Octal 
`printf("%o\n, 67)"` gives output `103`

`%x or X` gives unsigned hexadecimal number with `%X` being captialised

`%f or F` gives floats with `%F` being capitalised. Can be used with both `float` and `double` 

`%e or E` gives scientific notation with `%E` being capitalised e.g. `3.14159e+2`or `3.14159E+2`

`%g or %G` gives the most compact representation of the digit in either `%f` or `%e`. `%e` format is used if the mantissa is less -4

`%a or A` gives hex in lower or upper case

`%c` gives character

`%s` gives strings 

`%p` gives pointers e.g. `printf("%p", my_pointer)` prints address e.g. `0x7ffe6f71e60c`

`%n` prints nothing

`%%` prints a single % to the stream


# Length Flag

These go before the specifier and indicate the length of the data type. 

E.g. if you have a variable `long long double x` can be represented with `%llf` where `ll` denotes that is of `long long` and `f` denotes it of floating point decimal

`%hh% denotes signed char
