C Versions
The most recent specification of C is C23. The earlier versions of C include K&R C, C89, ANSI C, C 90, C95 and C99.

The most popular version of C is  C11. This is followed by C11, C17 and C18.

It is possible to determine which standard you are using to compile using this `-std=` tag when compiling. 
```bash
gcc -std=11 -pedantic foo.c
```

The `-Wall` tag when compiling gives common warnings. The `-Wextra` gives additional warnings.  The `-pedantic` tag tells the compile to strictly adhere to the ANSI standard - it turns off more extensions and generates more warnings. 
```bash
gcc -Wall -Wextra-std=23 % 
```