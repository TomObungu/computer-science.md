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
- Small side note, the hexadecimal above maps to some large number in order of magnitude of $10^{11}$. How is it possible to have this much RAM. Well it's actually just a large number being allocated with a virtual address in the physical RAM.

It is possible to define pointers and then assign the address of other variables to them. This is through the `&` operator. 
```C
int i; 
int *p;

p = &i
```


# 5.4 Dereferencing 
When you have a pointer to a variable, you alter the original variable through the pointer by dereferencing the pointer. 

```C
{
	int i;
	int *p;
	
	p = &i;
	
	i = 10;
	*p = 20;
	
	printf("i is %d\n", i);
	printf("i is $d\n", *p)
}
```

In the example code, the line `&p` indicates that the pointer holds the address of `i`.  This dereference operator is `*`. This means the value at the address is changed. Thus, the line `*p=20` is synonymous with the code `i=20`. 


# 5.4 Passing pointers as arguments (Passing by reference)

```C
 #include <stdio.h>

void increment(int *p) { // note that it accepts a pointer to an int
	5 *p = *p + 1; // add one to the thing p points to
}

int main(void){
	int i = 10;
	int *j = &i; // note the address-of; turns it into a pointer to i
	
	printf("i is %d\n", i); // prints "10"
	printf("i is also %d\n", *j); // prints "10"
	
	increment(j); // j is an int*--to i
	printf("i is %d\n", i); // prints "11"!
}
```

In the example code, it is possible to define a parameter as a pointer such as `int *p` then pass in the address of the variable into the function using the `&` operator. Altercations can be done the original variable by using the `*` dereference operator. Don't forget syntax to initialise a pointer is `int *j = &i`. You must pass the pointer into the function. 

You can also pass the address directly into the function like this:
```C
void increment(int *p) {
    (*p)++;
}

int main(void) {
    int i = 10;
    increment(&i);
}
```

# 5.5 The NULL pointer

You can set pointers to the `NULL` pointer if it doesn't point to anything. 

```C
int *p =;
p = NULL
```

Dereferencing it will produce undefined behaviour. 

Putting an asterisk in front of the variable name will turn it into a pointer.
```C
int *a, b, c, *d, e, *f, g, h, *i
```
In the code above `a`, `d`, `f` and `i` are all `int` pointers. 
