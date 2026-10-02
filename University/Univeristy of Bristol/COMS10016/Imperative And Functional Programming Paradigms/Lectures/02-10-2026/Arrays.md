# Feature Creep
In previous lectures advice was given to avoid quite a number of features, thus adding features to a language is not necessarily a good idea. In programming in C it would be possible to pefrom all computations using `while` loops only. However during eveloutions of languages, execessive features may be added that can be considered redundant. 

## Arrays
A sequence of related variables can be declared as a single array. Each individual array element is accessible via an index starting from `0`. 

Arrays are not initialised for efficiency  are initially undefined. Each element must be written before it is read. 

Constant-length arrays can be initialised compactly like this:
```C
int seq[3] = {10, 5, 4};
int seq[3] = {7, 9}
```
For fixed-length initialisation only, the compiler can work out the length of the array using inference:
```C
int seq[] = {10, 5, 4}
```

For the most part, we think that variables are stored contigously in memory. However C has no garuantee that the variables stored in contiguous memory. 

A declaration of array reserves one contiguous block of memory. The first element in the array is the pointer to contiguous block of memory. 

# Bugs
Indexing from `0` is usually helpful, but mistakes are still possible. Consider the code below:
```C
int seq[3];
seq[3] = 127;
```
This code below is trying to access out of bound memory. C does not automatically detect this. This may cause the program to run and produce garbage values or crash. Furthermore 

# Segmentation Faults
A segmentation fault or segfault is when your program tries to access memory which doesn't belong to it. An example code of a segmentation fault is below:
```C
int q = 3
int *p = q
int *p = NULL

printf("%p", p);
```

# Variable-length Arrays
Lengths of arrays can be variables. However the length of the array can't change after it is declared. It is only possible to do this using memory management. 
```C

```

# The Average Program
When passing in an array into a function as arguement. The length of the array must also be passed into function parameters. This only works if `n` is before the array 

# Pass-by-Reference
Array arugments can be passed by reference using pointers. This means that the actual array element is modified. Before the values edited were only copies from the array. 

# Returning of Arrays
Arrays can't be returned from functions directly. However it will be possible to return pointers to arrays that can be returned within functions. For example consider a function that adds two vectors
```C
void add(int n, double a[n], double b[n], double result[n]) {
	for(int i = 0; i < n; i++) {
		result[i] = a[i] + b[i];
	}
}
```

# Arrays of Arrays
2D matrices in C can just be defined as arrays of arrays. 
```C
int matrix[3][2] = {{1,4}, {5,3}, {9,2}};
printf("bottom right element: %d\n", matrix[2][1]);
```