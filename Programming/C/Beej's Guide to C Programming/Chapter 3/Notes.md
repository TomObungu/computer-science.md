In C a string can be represented as a `char *.

Recall that `printf()` can take in arguments using the `%` sign. `%d` stands for integer. `%f` stands for float and so on:
```C
printf("%d, %d\n", i, j); 
```


The `sizeof` operator tells you the size in bytes that a particular variable or data type uses in memory. 

This can be different on different systems, except for `char` which is always 1 byte. 