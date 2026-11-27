# Variable Length Argument Lists
C allows variadic functions with any number of types and arguments. The `printf` function is an example a function that allows taking a variable number of arguments. 
```C
int printf(const char* format, ...)
```
The `...` indicates the function receives a variable number of arguments of any types. 