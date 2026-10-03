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

You use `fscanf` like you would when doing `scanf` or `printf` with the `%` specifiers

E.g if you have a file with lines like this:
```
...
blue 29.9 173
right 20.7 135
...
```

Use `fscanf` to parse the lines based on the white spaces

```C
scanf(fp, "%s %f %d", name, &length, &mass)
```


Thus below is an example to parse a text file separated by whitespaces

```C
1 #include <stdio.h>
2
3 int main(void)
4 {
5 FILE *fp;
6 char name[1024]; // Big enough for any line this program will encounter
Chapter 9. File Input/Output 60
7 float length;
8 int mass;
9
10 fp = fopen("whales.txt", "r");
11
12 while (fscanf(fp, "%s %f %d", name, &length, &mass) != EOF)
13 printf("%s whale, %d tonnes, %.1f meters\n", name, mass, length);
14
15 fclose(fp);
16 }
```

# 9.5 Writing Text Files

In the same we can use `fgetc`, `fgets` and `fscanf` to read and parse text streams.

`fputc`, `fputs` and `fprintf` are their writing equivalents. 

This through using `fopen`  in `w` mode instead of `r`. 

Below is code snippet that utilises the functions 

```C
1 #include <stdio.h>
2
3 int main(void)
4 {
5 FILE *fp;
6 int x = 32;
7
8 fp = fopen("output.txt", "w");
9
10 fputc('B', fp);
11 fputc('\n', fp); // newline
12 fprintf(fp, "x = %d\n", x);
13 fputs("Hello, world!\n", fp);
14
15 fclose(fp);
16 }
```

It produces a text file like this
```
B
x = 32
Hello, world!
```

As mentioned earlier, `stdout` is its own file stream thus you could replace `fp = stdout` and it will write to the terminal/screen. 

# Binary File I/O

You can read an array of bytes and write them to a `.bin` file using `fread` and `fwrite`. When opening the `.bin` file ensure `b` is added to to `fopen`. 

Below is a program that will write the binary equivalent the data in the array 

```C
include <stdio.h>
2
3 int main(void)
4 {
5 FILE *fp;
6 unsigned char bytes[6] = {5, 37, 0, 88, 255, 12};
7
8 fp = fopen("output.bin", "wb"); // wb mode for "write binary"!
9
10 // In the call to fwrite, the arguments are:
11 //
12 // * Pointer to data to write
13 // * Size of each "piece" of data
14 // * Count of each "piece" of data
15 // * FILE*
16
17 fwrite(bytes, sizeof(char), 6, fp);
18
19 fclose(fp);
20 }
```

Running the output in the `.bin` file will give the binary output
```
05 25 00 58 ff 0c
```

Below is a neat example that takes in the input of a file and then stores them in a struct.

```C
void parse_file(const char* file_name){
	FILE* fp;
	
	struct person individual;

	fp = fopen(file_name, "r");

	if(fp == NULL) {
		printf("Error opening file");
		return;
	}


	while(fscanf(fp, "%32s %hu %4s", individual.name,
		&individual.age, individual.height) != EOF)
		printf("Name : %s, Age : %hu, Height : %s \n", individual.name,
			individual.age, individual.height);	

	fclose(fp);
}

```

Things learnt are that you must pass into pre-defined arrays into const chars in structs otherwise you'll get a segfault. It is possible to overcome this through memory allocation which can be defined later. 

You must also define the size of the array to be `+ 1` to considerate the extra null character
```C
struct person {
	char name[33];
	unsigned short age;
	char height[5];
};

```

Buffer checks can be done using `$xs` where `x` is the maximum size of the string. e.g `54s`It is good practice to do the `(x-1)s` minus one to discard the null terminator `\0`

You can also define the maximum length of your inputted strings like this
```C
...
fscanf(fp, "%32s %hu %4s", individual.name
...
```

