"All existing machines using direct addressing that is to say every item in memory has its own numerical address and position in memory" - John Von Neumann. 
# Structures of Memory
A C program has access to a computer's memory as an array of Bytes. Each byte has a unique position index, which is call the address of the byte.  
Some parts of the memory belong to the program and other parts to other programs. 
![[Pasted image 20261012102507.png]]
# Multi-byte Variables
Consider the data type of an `int`. An int consists of 4 bytes, thus the addresses go up in 4's. However remember that relative to the `int` data type in a array, the indexes go up in $0$, $1$ and $2$.
![[Pasted image 20261012102513.png]]
## Pointers
A pointer essentially holds a reference in memory. In C, pointers are variables which live in memory like any other variable. They are usually 8 byte integers (64 bit integers). Pointers can be typed to keep information about the type of the item stored at that address. 

Pointers will point to random positions in memory until it is initialised. Printing the uninitialised variables will yield undefined behaviour.

The pointer variable can be initialised by the address operator `&` which has been using `scanf`
```C
p = &k;
```

In arrays in C, arrays are pointers to the first elements in the usually contiguous chunk of memory.

```C
int a[3] = {2, 4, 6}
int *p = a; // Points to the first element of the array only
```
# Notational Meaning
Beware that the line below means that a pointer is initialised and then assigned to address `x`.
```c
int *p = x
```
However the line below means that a pointer to an int `p` is declared and regular int `q`
```C
int *p; int q;
```

## Pointer Arithmetic
If a pointer variable `int*`  points to an int, then `p++` or `p+1` points one `int` further on. That is jump one `sizeof(int)` in bytes within the memory. 

The `void` pointer type is a generic pointer to memory. However `void` pointers cannot be dereferenced or have pointer arithmetic applied to them. 

# NULL
The special `NULL` operator is found in `stdio.h`. It is identical to `0` filled with `0`. It is unusable and belongs to the OS. It is used as an error indicator. 

# Pointers, arrays and string constants
The lines of code below would be identical however `char *p` is a fixed string constant. However if the string is indeed fixed, then s is less efficient for a long string as it allocates more memory. 
```C
char s[] = "bat";
char *p* = "bat";
```

# Pass-by-reference and Array returns
It possible to return arrays from functions via pointers!
```C
char* upperCase(char *s)
```

# Dangling Pointers
The code blow has a problem due to the variable `s` going out of scope. It will yield undefined behaviour as `s` is on the stack goes out of scope. It returns what is known as a dangling pointer. 
```C
char *show(int n) {
	char s[12];
	itoa(n, s, 10); // convert integer to string with base 10
	return s; // MAJOR BUG: since s goes out of scope here
}
```

There is no dangling pointer problem if we return an actual argument to a poiner:
```C
char *min(char *s1, char *s2) {
	if (strcmp(s1,s2)<0) return s1;
	return s2;
}
```
Furthermore there is no dangling pointer problem is the heap is used to allocate memory. 

# Main Signatures
The `main` function takes in as a second argument an array of n pointers to char array `args`
```C
int main(int n, char *args[n]) {
}
```

However these notations are identical
```C
... int main(int n, char **args) {...} ...
... int main(int argc, char *argv[argc]) {...} ...
... int main(int n, char *args[]) {...}
```