"All existing machines using direct addressing that is to say every item in memory has its own numerical address and position in memory" - John Von Neumann. 
# Structures of Memory
A C program has access to a computer's memory as an array of Bytes. Each byte has a unique position index, which is call the address of the byte.  
Some parts of the memory belong to the program and other parts to other programs. 
# Multi-byte Variables
Consider the data type of an `int`. An int consists of 4 bytes, thus the addresses go up in 4's. However remember that relative to the `int` data type in a array, the indexes go up in $0$, $1$ and $2$.

## Pointers
A pointer essentially holds a reference in memory. In C, pointers are variables which live in memory like any other variable. They are usually 8 byte integers (64 bit integers). Pointers can be typed to keep information about the type of the item stored at that address. 

Pointers will point to random positions in memory until it is initialised. Printing the uninitialised variables will yield undefined behaviour.

The pointer variable can be yielded by 