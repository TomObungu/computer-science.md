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


# The Stack example
Consider a program that has a `main()` function body that reserves a `float`, and array of `floats` in such manner:
```C
float fDist;
float fV1[] = { 4, 10, 12}
float fV2[] = {14, 1}
```
On the stack this would look like. Assume that the stack is 1MB.  The main function is the most active functional call on the stack frame
![[Pasted image 20261019102132.png]]
Consider another function `L2norm` that computes square root of a square differences of two floating point numbers that contains variables and a for loop
```C
float L2norm(float fV1[], float fV2[], int n)
...
int i;
float fSum = 0
for (int i = 0; i < n; i++)
	fSum +=
...
```
When this function is called, it pushed onto the stack and its variables become the most active varibles within the program scope
![[Pasted image 20261019102711.png]]
When the function `L2Norm` has finished executing and returns. It's variables and function call are pushed off the stack and the variables of `main()` are set in use again.
![[Pasted image 20261019102132.png]]


# The Heap Example
Consider a function in C that uses the `malloc` function to allocate 6 floats on the heap
```C
flaot * makeRand6DvectorRIGHT()
{
	int i;
	float * fA = (float*) malloc(sizeof(float)*6);
	
	for (int i = 0; i < 6; i++)
		fA[i] = (float)(rand() % 100);
		
	return fA;
}
```
The call of `malloc` within the variable `fA` will allocate a variable on the stack in such manner
![[Pasted image 20261019103146.png]]

# Stack Dynamics
Below is an example growing and shrinking a stack during a recursive call sequence. 
![[Pasted image 20261019103452.png]]

The stack grows and shrinks at random. The stack has limited size (for instance this can be `8192`KB) on some linux systems cotrolled by the terminal command `ulimit -s 8192`

# Heap Dynamics
The heap is used for dyanmically allocated memory. The most common case is an array or any other data structure which needs to be persistent throughout function calls and/orneeds to shrink or grow dynamically. The heap is managed by the malloc and free libraries functions from stdlib.

The heap never shrinks but gaps appear after `free`. `malloc` searches for the best gap, `free` merges `gaps` and both use a header at the start of allocations and gaps to keep track of everything. 

# Calling `malloc`
The return type of malloc is `void*` whi