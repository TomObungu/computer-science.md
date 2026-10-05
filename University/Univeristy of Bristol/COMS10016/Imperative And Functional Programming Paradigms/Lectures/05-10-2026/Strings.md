Strings are sequences of characters. Chars are 8-bit integer numbers. It is possible to initialise them with single quotes like below:
```C
char a = 65;
char b = 'b'
```

# Numbers -> Characters
The btyes for a character hold a number. Each number needs to abstractly represent a character. This requires a standard. The standard that maps each number to a character is called ASCII. 

# Digits
Subtracting `0` from the literal character representation of digit will yield it's difference. There is a constant difference of '0' between digits and their character representations.
```C
char svn = '7' - '0'
```
There is a constant difference of `32` between lower and upper characters. It is also advisable to use the `toupper` command rather than using raw subtractions. 

To print a single quote use `\n`. 

# Null character
The null character is the byte with every bit off. The null character has binary representation of $00000000$ which is $0$. Where as the character zero actually has value $48$.

For string arrays, there must be one more byte than visible characters. 

# NULL terminator
In C, arrays do not know their own length. `printf` and every other string function are only told where the string starts. They will continue in memory until the null terminator is found. However if no NULL terminator.

There is a difference between the `NULL` keyboard and the NULL terminator. 
```C
int* myptr = NULL // NULL -> The NULL pointer. 64 bits on most machines
char mychr = '\0' // Null terminator. 8 bits (1 byte) on machines
```

Not null-terminating your strings can lead to out of bounds errors and segmentation faults. 

To initialise a string you must use double quotation marks `""`  to automatically initialise strings.  This means the data representation will automatically have the `\0` character at the end of the string. 

The `strln` from `string.h` provides the functionality to calculate the size of a string. The `size_t` return type is an unsigned integer type evaluated at a compile time. 

For must cases C, treats an array of characters and pointers to the first value in an array as the same thing. That the function declartions are the same
```C
size_t strln(const char* str) 
size_t strln(const char str[]) 
```

You can use the `"%zu"` format specifier in `printf()` when dealing with `size_t`.

# Input from the command line
So far, programs get their input from `scanf` while running. However it possible to use command line arguments.
