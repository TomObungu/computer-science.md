All input and output in C is based on the concept of streams. These are sequences of bytes. The three pre-defined streams are `stdin`, `stdout` and `stderr`. The command `fprintf(stdout, "Hi");` outputs the two characters to `stdout`.

Many I/O operations in C are flawed and can pose security risks. 

# I/O Functions

- `fopen, feof, fclose` - Open file, check whether reached the end of the line, close a file
- `fgetc` - Read chars/bytes from file
- `fgets` - Read lines from file
- `getchar` - Read chars from `stdin`
- `fputc` - Write chars to file
- `fprintf` - Write lines to file

# File Handlers
A file name is associated to a so called handle variable of type `FILE*` via `fopen`