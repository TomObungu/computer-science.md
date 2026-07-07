Other language like Javascript, Python all use garbage collection but in C you must manage all the memory yourself. 

In C some variables are automatically allocated and deallocated such as variables on the **stack**. 

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

It is possible to specify the number of bytes of memory, using like this 
```
char *p = malloc(3490)
```


## `calloc`
The `calloc` function takes in the size of one element and the number of elements you wish to allocate. The `calloc` function 

