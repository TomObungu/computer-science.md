Recall that the program is stored with the text segment, data segment and unitialized data. The machine code is loaded when the program is run. The heap expands upwards and the stack expands downwards. 

# Function Pointers
Function pointers have the function's type signature as their pointer types
```C
int square(int x) { return x * x};
int (*f)(int);
f = square;
```

# Arrays of Function Pointers
It possible to have function selection using function pointers
```C
typedef int op(int x, int y);
enum opcode { Plus, Minus, Times, Over };
op *ops[] = { add, subtract, multiply, divide };
...
int main(){
    op *f = ops[Times];
    int n = f(6,7);
```

