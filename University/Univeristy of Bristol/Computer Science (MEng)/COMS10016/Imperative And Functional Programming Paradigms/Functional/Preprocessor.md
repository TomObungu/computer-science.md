Preprocessors are run before the compiler. Preprocessors find/replace code sections according to the preporcessor directives (symbols starting with `#`).
# Macros with Arguments
Macros with arguments are substituted into the replacement text then the macro is expanded:
```C
#define PI 3.14159
#define DISC(radius) ((PI)) * (radius) * (radius)
```
After preprocessing this expands to:
```C
double area = DISC(r+4)
double area = ((3.14159) * (r+4) * (r+4))
```

# `\` and `#undef`
A backslash can be used at the end of the line in the the case the replace continues onto the next line:
```C
#define CUBE(argument) ((argument) * \ 
						(argument) (argument))
```
Macros can be given limited scope by using the `#undef` and `#define`. Macros are not type checked.
# Inline functions
`inline` is a hint to the compiler that calls to a function may be replaced with a copy of the functions code by the compiler. Inline's use type-checks can remove overheads in  time-critical programs:
```C
inline int square(int x){returns x * x}
	int b = 5;
int c = square(b) // Function may not be called but inlined
```
This means the call to `int c = square(b)` is simply replaced with 
```C
...
int c = b * b
...
```
A compiler can ignore the `inline` request all together. A function will be defined `inline` will not, and one defined `extern inline` will always be usable via other modules when using the compiler option `-flto`.
# `#` and `##`

The `#` operator turns a replacement text into a string surrounded by quotes: `#define PRINT(X) printf( #x)`. That is when `PRINT(Welcome)` appears in a program, it is expanded to `printf("Welcome")`. 

The `##` operator concatenates two tokens defined like:
```C
#define CONCAT(x,y) x##y
```
The following program snippet shows and example:
```C
#define CONCACT(x,y)
int hello = 5;
printf("%d\n", CONCAT(hel,lo));
```

# Symbolic Constants and `#pragma`
`__LINE__`  - The line number of the current source code
`__FILE__` - The presumed name of the source file
`__DATE__` - The date the source file was compiled from `Mmm dd yyyy`
`__TIME__` - The time the source file was compiled (a string literal `hh:mm:ss`)

The `#pragma` directive is an implementation-defined action, e.g. `#pragma startup f` will run `f()` before `main()` and `#pragma exit g` will run `g()` before the program exits. 
# Double `Enum` Inclusion Problem
Problems can occur if a shared module has enumerations and included twice. This can be fixed by turning the `enum` to `extern const`
```C
extern intsuit {Club, Diamond, Heart, Spade};
typdef int suit;
```

This can also be fixed by protective `#ifdef` and `#ifndef` guards which prevents it from being included twice. 
```C
#ifndef HEADER_IS_INCLUDED
#define HEADER_IS_INCLUDE
	extern intsuit {Club, Diamond, Heart, Spade};
	typdef int suit;
#endif
```

You can also do it using conditional compilation as well:
```C
#if !defined(HEADER_IS_INCLUDED)
#define HEADER_IS_INCLUDED
extern intsuit {Club, Diamond, Heart, Spade};
	typdef int suit;
#elif
#endif
```
# Automatic Testing Via Compiler Flags
It is possible to use conditional compilation to switch on and off auto testing depending on a name defintion provided by a compiler flag. 

It is possible to include `main()` and testing in the compilation or not. That is you want to include `#ifdef list_test` you include the `-Dlist_test` tag
```shell
gcc -std=c11 -Wall -Dlist_test list.c -o list
```

