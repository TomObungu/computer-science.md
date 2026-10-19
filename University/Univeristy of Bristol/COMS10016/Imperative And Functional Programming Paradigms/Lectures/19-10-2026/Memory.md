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

# The stack
The stack is the memory set aside for local variables, bookkeeping data. Whenever a function returns, whatever block on the stack the function held becomes unused and free to be used by another function. The stack is always reserved in a LIFO order. 

Free a block on the stack can be seen as adjusting just on pointer
# The heap
The heap is memory specifically set aside for dynamic allocation. Unlike the stack, you can allocate a block at any time and free it at any time. This makes it much more complex to keep track of which parts are allocated. A problem with the heap is that memory can end up being non-contiguous whereas on the stack the memory can be 

# Virtual Memory
In higher order abstractions on levels of C software. The memory represented on the heap may seem to be contiguous but on the lower level. The virtual memory addresses can be comprised of specific chunks of RAM memory and disk memory.
![[Pasted image 20261019101545.png]]