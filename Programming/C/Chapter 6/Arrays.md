# 6.1
To declare an array you do this
```C
float f[4];
```

Arrays are just pointers to the first element in a contiguous list of memory. 

# 6.2 Getting the length of an array
To get the length of an array, you must use `sizeof` on the whole array and then divide it by the `sizeof` of the type:
```C
int x[12];

printf("%zu\n", sizeof(x)); // 48 total bytes
printf("%zu\n", sizeof(int)) // 4 bytes per int
```
Thus the total size is given by:
```C
printf("%zu\n", sizeof(x) / sizeof(int)) // 12 ints!
```

Passing arrays into functions will not work as it only passes in the pointer to the first element in the array. 
```C
void foo(int x[12]){
	printf("%zu\n", sizeof(x)); // only prints out 8 not 48
	printf("%zu\n", sizeof(int)) // prints of 4 
	printf("%zu\n", sizeof(x) / sizeof(int)) // prints out 2 
	
}
```

To pass in arrays into functions you need to have a pointer to the array.

# 6.3 Array initialisers

You can do something like this
```C
int a[5] = {256, 2048, 18}
```

The rest will be filled with `0

You can create an array filled with `0` or some number by doing

```C
int a[100] = {0};
// 
int a[100] = {5};
```