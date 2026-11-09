Recall that the program is stored with the text segment, data segment and unitialized data. The machine code is loaded when the program is run. The heap expands upwards and the stack expands downwards. 

# Function Pointers
Function pointers have the function's type signature as their pointer types
```C
int square(int x) { return x * x};
int (*f)(int);
f = square;
```

