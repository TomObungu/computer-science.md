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
A file name is associated to a so called handle variable of type `FILE*` via `fopen
```C
FILE* fopen(char* filename, char* modes);
```

## Opening files
The modes string describes the different ways a file can be opened as:
- `r` - Open a file for reading
- `w` - Open a file for writing
- `a` - Open text file for appending
- `rb` - Open binary file for reading
- `wb` - Open binary file for writing
- `an` - Open binary file for appending

If the file cannot be found, written or if it is not readable, then fopen function returns `NULL`

# Closing Files
You must close a file when you have finished processing it. The file isn't closed until the program ends and you may reach the small limit on the number of open files on your OS. 

In Linux, the root user could this script to learn about open file handles:
```shell
cd /proc
for pid in [0-9]*
do
	echo "PID = $pid with $(ls /proc/$pid/fd/ | wc -l) file with descriptors"
done
```

# Structured Input
Once a line is read from the file, to read numbers and name from a string, one per line, you can use `sscanf(line, "%d %s", &n, name)`

## Specifiers
`%s` in `sscanf` reads in a word up to the next space. Instead use the conversion specifier `%[ ]` for strings with spaces. 

You can use `%[^,]%*c` to read everything up to (just before) a comma and then discard the comma. The `%[]` means to read a character, the `%[,]` means to read a character up to a comma and the `^` means to ignore it. The `%*c` then means to 
## Removing New Line Markers
If you want to get rid of a newline at the end of a string  you've just read in, this is another compact technique. 
```C
line[strcspn(line, "\r\n")] = '\0';
```
The function `strcspn` calculates the length of the number of characters present in both strings, then this index is used to terminate the string right there before the newline. This is cross-platform (it handles `\n` `\r\n`) and it works on strings which don't have a newline. 

Don't use functions like `getline` and `readline`. They are not part of the `stdlib`  and are not even available on some other platforms. 

## Efficiency
Often physical `I/O` is very slow so much so the efficiency of the code itself becomes irrelevant. However when it matters, reading a line at a time is faster than reading a character at a time. 

For maximum efficiency, use `fread` to transfer the whole file into a string `s` at once.

Use the `fseek` function to manipulate the current file position 

Use the `ftell` to get the file length (so you can get enough memory for `s`):
```C
FILE *fp = fopen(path, "rb");
fseek(fp, 0, SEEK_END);
long length = ftell(fp);
fseek(fp, 0, SEEK_SET);
fread(s, length, 1, fp);
fclose(fp);
```