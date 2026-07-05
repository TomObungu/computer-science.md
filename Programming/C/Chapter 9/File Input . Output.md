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

`fgetc` gets a character from the file stream. Subsequent calls to `fgetc` will get the next character and so on. 

# 9.3 `EOF`

`EOF` is a special character  macro. Once `fgetc` is reaches the end of the file it will return it. Its type is not `char`. That is why when you are defining the variable to store the result of `fgetc`, you define it as an `int`. Anyway this the code to print the contents of a file using `fgetc`

```C
1 #include <stdio.h>
2
3 int main(void)
4 {
5 FILE *fp;
6 int c;
7
8 fp = fopen("hello.txt", "r");
9
10 while ((c = fgetc(fp)) != EOF)
11 printf("%c", c);
12
13 fclose(fp);
14 
```


## 9.3.1 Reading a line at a time

To read an entire line at once you use `fgets` instead of `fgetc`. You need to have a char array of suitable size to store the line 
```C
1 #include <stdio.h>
2
3 int main(void)
4 {
5 FILE *fp;
6 char s[1024]; // Big enough for any line this program will encounter
7 int linecount = 0;
8
9 fp = fopen("quote.txt", "r");
10
11 while (fgets(s, sizeof s, fp) != NULL)
12 printf("%d: %s", ++linecount, s);
13
14 fclose(fp);
15 }

```


# 9.4 Formatted Input
You can use `fscanf` to skip leading whitespaces when reading and return `EOF` on end-of-file or on errors. 

You use `fscanf` like you would when doing `scanf `