static functions cannot be used in any other module because they are not linked across modules. If you want to make function local to a module, leave it out of the header file and define it as `static`.

Static functions are not provided to the linker and thus can only be used within a module within one object file. 

# The build process and linking
The process of turning source into an executable program can be broken down. For example you can use `gcc` to form object files and then link the object files into a program:
```shell
gcc -std=c11 -c print.c main.c 
gcc -std=c11 -Wall print.o main.o -lm -o main
```

Static functions are not provided to the linker and, thus, can only be used within a module in one object files. 

The benefit of producing object files first and linking them is that you will not need to recompile unchanged files, only files that are changed will need to be recompiled and then can be linked into the binary.

# `extern`
Any function that is not `static` is by default compiled as `extern` such as `print()`. Thus `void print(){}` and `extern void print(){}` are identical. 

Remember `extern` means make it available to the linker to linked.

When using global variables which are defined in other modules, use `extern` to refer to. For example to use a variable `a` to be used in `storagea.c` from `storageb.c` 
```C
externa int a;
```

By default local variables are compiled as `auto`, which means they are allocated on the `STACK` and their values vanish once out of scope. The two modules are identical. 
```C
f() {
int b = }
```
```C
f() {
auto  int b = }
```

However if a local variable is `static` it will initialised only once per DATA segment and will remain a valid value until the program ends:
```C
int g(){
	static int c = 5; // runs only once
	c++
	return c;
} // first returns 6, called 7, 8 again
```

# Storage Classes
A local variable can also be defined as `register` which means the compiler tries to allocate the variable to fast storage within the process (optimisation may do this anyway), but there is no gaurantee:
```C
register int l =
```