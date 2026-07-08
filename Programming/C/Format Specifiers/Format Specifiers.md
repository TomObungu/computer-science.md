https://www.geeksforgeeks.org/c/format-specifiers-in-c/

https://cplusplus.com/reference/cstdio/printf/#google_vignette

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

`%f or F` gives floats with `%F` being capitalised. Only matters 

`%e or E` gives scientific notation with `%E` being capitalised e.g. `3.14159e+2`or `3.14159E+2`


`%s` gives strings

