# 5. 1 Memory and Variables
A pointer is a variable that holds an address. 

In the `%p` specifier prints a pointer

```C
#include <stdio.h>

int main(){
	int i = 10;
	
	printf("The value of i is %d\n", i);
	printf("The address of i is %p\n", (void *)&i);
}
```
 
The `&` operator indicates the address of i and the `(void*)` type cast is there to stop the compiler from throwing a warning or whatever. 

This prints out 
```
The value of i is 10
And its address is 0x7ffddf7072a4

```
- Sma