# Pointer Arithmetic
You can increment from a pointer like this. It is useful for arrays. This does not modify the value of the pointer
```C
int a[5] = {11, 22, 33, 44, 55};
int *p = &a[0]; // Or "int *p = a;" works just as well
for (int i = 0; i < 5; i++) {
printf("%d\n", *(p + i)); // Same as p[i]!
}
```

In pointer arithmetic. Array notation can be expressed as pointer arithmetic
```C
a[b] == *(a + b)
```

```
E1[E2] is identical to (*((E1)+(E2)))
```

# 11.1.3 Subtracting Pointers
It is possible to subtract pointers to find the differences in positions in arrays

```C
1 #include <stdio.h>
2
3 int my_strlen(char *s)
4 {
5 // Start scanning from the beginning of the string
6 char *p = s;
7
8 // Scan until we find the NUL character
9 while (*p != '\0')
10 p++;
11
12 // Return the difference in pointers
13 return p - s;
14 }
15
16 int main(void)
17 {
18 printf("%d\n", my_strlen("Hello, world!")); // Prints "13"
19 
```

Above is an implementation of `strlen` using pointer arithmetic 


# 11.3 `void` Pointers

Void pointers are pointers that indicate that type of the thing being pointed to is not known. This is useful as it can be used in functions to have flexibility. 

There two main use cases to void pointers
1. If a function is operating on something byte-by-byte. E.g. the function `memcpy` copies bytes from memory to one pointer to another but the pointers can be any type. 
2. If using function pointers to pass another function into a callback function. In this case the function calling the passed 

Let's take a look at the `memcpy` function. 

```C
void *memcpy(void *s1, void *s2, size_t n)
```

The function copies `n` bytes of data from address `s2` to the memory address starting at `s1`. 

The special thing is that parameters are both `void*`. 

This allows having a pointer to a source of and pointer to a destination and the number of bytes you want to copy, you can copy any type of data. 

Below is an example of `memcpy` working for the `int` array data type:

```C
#include <stdio.h>
#include <string.h>

int main(void){
	int a[] = {11, 22, 33};
	int b[3];
	
	memcpy(b, a, 3 * sizeof(int)); // copy 3 ints of data
	
	printf("%d\n", b[1]) // prints 22
}
```

The goodness of `void*` is that we could even copy a `float` or a `struct` with `memcpy()`

```C
struct my_struct;
struct my_clone_struct;
// ...
memcpy(&my_clone_struct, &my_struct, sizeof(my_struct)));
```

However when dealing with structs you must use `=` instead of `memcpy`

If `void*` didn't exist. We'd have to write a specialized `memcpy` functions for each type of data required like this:

```C
nemcpy_int(int *a, int *b, int count);
memcpy_float(float *a, float *b, int count);
memcpy_double(double *a, double *b, int count);
memcpy_char(char *a, char *b, int count);
memcpy_unsigned_char(unsigned char *a, unsigned char *b, int count);
// etc... blech!
```

Much better to use `void*` and have one function that can do it all. 

However if the type if `void*`, there are things you cannot do:
1. You can't do pointer arithmetic on them
2. You can't dereference them
3. You can't use arrow operator as that's a derefernce
4. You can't use array notation as that's also a dereference. 

However a way overcome this is via converting the `void *` to another type before using it.  It possible to do this by assigning the variable of the desired type:
```C
char a = 'X';

void *p = &a; // points to 'X' // cannot dereference this
char *q = p // q also points to the 'X' // 
```

The void pointer can point to any type but the type `void *` itself can converted to another type

Here is an example in a custom defined `memcpy` function:

```C
void *my_memcpy(void *dest, void *src, int byte_count)
{
	char *s = src, *d = dest
	
	while(byte_count--)
		*++d = *++s;
		
	return dest;
}
```


In casting  a `void *` to a char *  is permitted by the language standard. The resulting pointer points directly to the first byte of the structure.  This is because sizeof(char) is exactly 1 byte in C. Incrementing a char * by one moves the pointer forward exactly one byte. This allows stepping through the entire memory footprint of the structure. 

In the case of `structs` owever there is a problem of padding bytes. Compilers automatically insert invisible, unused bytes between data types. If you compare two identical data t
