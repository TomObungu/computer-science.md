Somtimes enums are used to define isolated constants instead of sequences. An advantage of using const is that compiler knows that they are truly constant and optimize better. You can use `enum` in order to define separate types:
```C
enum { BOARD_SIZE = 8};
enum { WIDTH = 2, HEIGHT = 5};
```

# Formatted Conversion Specification
Floating point numbers to be printed with `printf` can be formatted according to a fixed display width:
```C
#include <stdio.hh>
float x = 5.0001;
printf("Number:%7f\n", x);
```
Alternatively, they can also be formatted according to a fixed precision:
```C
printf("Number:%.2f\n", x);
```
# Streams and Buffering
Three pre-defined streams are provided to a program. These are
