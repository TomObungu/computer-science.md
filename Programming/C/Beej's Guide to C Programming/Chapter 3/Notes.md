


In C a string can be represented as a `char *.

Recall that `printf()` can take in arguments using the `%` sign. `%d` stands for integer. `%f` stands for float and so on:
```C
printf("%d, %d\n", i, j); 
```

# 3.2.4 The Comma Operator

The comma operator always takes the right most expression 

```C
int x = (1,2,3);
printf("%d", x); // prints 3
```

# 3.2.7 The sizeof Operator
The `sizeof` operator tells you the size in bytes that a particular variable or data type uses in memory. 

This can be different on different systems, except for `char` which is always 1 byte. 

The sizeof operation returns a `size_t`

The `size_t` data type is an unsigned integer type that can return a different size in bytes at compile time. E.g. If the parameters passed into the `sizeof` function is an integer it will return 4 but if it is a float, it will return 8. 


```c++
printf("%zu\n", sizeof(a)); // prints 4 on my system
printf("%zu\n", sizeof(3.14)); // prints 8 on my system
printf("%zu\n", sizeof(int)); // prints 4 on my system 
```

# 3.3.4 The `for `

