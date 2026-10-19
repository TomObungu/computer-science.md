# Skinny Memory Allocation in C
If you require lots of memory that needs to persist until you free it explicitly, you need `malloc`. This memory is allocated on the heap
```C
int * ip = malloc(N*sizeof(int)); 
```

Variables declared without `malloc` are allocated on the stack and freed when the function in which they are declared returns. This is what happens when variables are declared normally:
```C
int iArr[N];
```

## A Program's Memory Space
The machine code of the program consists of a text segment and data segment with constants. The program also contains uninitialised data when the program is run. 

The heap expands upwards and the stack expands downwards.
![[Pasted image 20261019100759.png]]