Other language like Javascript, Python all use garbage collection but in C you must manage all the memory yourself. 


# Stack
In C some variables are automatically allocated and deallocated such as variables on the **stack**. 

Below is a diagram explaining the stack. 

![[Pasted image 20260707114854.png]]

The stack is orded and al


How manual memory allocation happens on the **heap**. 


In C you can tell C to explicitly allocate a certain number of bytes that you can use you please. These bytes will remain allocated until that memory is explicitly freed. 

When using manual memory allocation routines in C. You must include the `stdlib.h` header. 


# 12.1 Allocating and Deallocating, `malloc` and `free`
The `malloc` function accepts a number of bytes to allocate and returns a void pointer to that block of newly allocated memory. Since it is a void pointer, you can assign it to whatever type you want. Recall that `sizeof` is in bytes. The pointer storing the result of `malloc` is identical to an array of the size allocated by `malloc`. 
```C
#include <stdlib.h>

int main(void){
	int* p = malloc(sizeof(int) * 12)
	
	p[0] = 12;
	
	printf("%i", p[0]);
}
```

It is also good to add error checking to avoid undefined behaviour
```C
int *x;

x = malloc(sizeof(int) * 10);

if (x == NULL) {
	printf("Error allocating 10 ints\n");
// do something here to handle it
}
```

Below is an example in which the memory is allocated  and `free` is called at the end of the program 

```C
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
	// Allocate space for 10 ints
   int *p = malloc(sizeof(int) * 10);

   // Assign them values 0-45:
   for (int i = 0; i < 10; i++)
   p[i] = i * 5;

	// Print all values 0, 5, 10, 15, ..., 40, 4
	for (int i = 0; i < 10; i++)
	printf("%d\n", p[i]);

	// Free the space
	free(p);
}
```

# 12.3 Allocating space for an array

## `calloc`
The `calloc` function takes in the size of one element and the number of elements you wish to allocate. The `calloc` function 

```C
int *p = calloc(10, sizeof(int))
```


# 12.5 Changing Allocated Size with realloc()

`realloc` can resize the memory pointer that was formed by using `malloc` or `calloc`. 

This is useful for later on things like implementing dynamic array data structures or having variable size input at runtime. 

When calling `realloc` you must specify the number of bytes to allocate. Not just the elements. This usually means multiplying by the `sizeof(x)` where `x` is the data type. 

```
float num_floats *= 2;

np = realloc(p, num_floats * sizeof(float))
```


Below is a code example that show first allocating space for 20 elements then resizing the space for 40 elements

```C
float *p = malloc(size *p * 20);

float *new_p = realloc(p, sizeof *p * 40);
```

Now we can also assign `p` to `new_p`. Doing so will cause `p` and `new_p` to point to same chunk of memory, so called `free(p)` will free free both

```C
p = new_P
// at the end of the program 
free(p)
```
