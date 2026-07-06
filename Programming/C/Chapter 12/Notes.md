When using manual memory allocation routines in C. You must include the `stdlib.h` header. 

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

The `calloc` function 