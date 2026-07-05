# 9.1 The FILE* Data Type

When dealing with I/O in C, we do so through the `FILE*` data type

Of the `FILE*` data types there are 'streams' where data can travel. Here are the various stream in which data can travel 

| `FILE*`  |                                                                          |
| -------- | ------------------------------------------------------------------------ |
| `stdin`  | The standard input stream. This generally from the keybaord              |
| `stdout` | The standard output stream.  Generally the screen or terminal by default |
| `stderr` | The standard error stream. Generally the screen or terminal by default.  |


For example you can use `fprintf` and specify the stream as `stdoit`. This yields a command identical to `printf` as `printf` sends data to `stdout` by default

```C
printf("Hello, world!\n");
fprintf(stdout, "Hello, world!\n"); // printf to a file
```

It is possible to redirect the output of `stdout`  or `stderr` o different files. 

For example, here is a UNIX like command to send data to the non-error data to one text file and the error data to another text file
```
./foo > output.txt 2> errors.txt 
```

# 9.2 Reading text files

Below is the code to read a text file

```C
1 #include <stdio.h>
2
3 int main(void)
4 {
5 FILE *fp; // Variable to represent open file
6
7 fp = fopen("hello.txt", "r"); // Open file for reading
8
9 int c = fgetc(fp); // Read a single character
10 printf("%c\n", c); // Print char to stdout
11
12 fclose(fp); // Close the file when done
13 }
```

We've open the file as `"r"` which means to open the file for reading. 


`fopen` returns `NULL` if something goes wrong