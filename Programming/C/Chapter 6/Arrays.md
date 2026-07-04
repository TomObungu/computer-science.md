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

Passing arrays into functions will not work as it only passes in the 