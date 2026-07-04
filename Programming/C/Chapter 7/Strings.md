7.1 String Literals

You can represent strings like sentences using double quotation marks as string literals E.g. `"Hello, world!"`

In C you can put the quotation marks inside a string using:
```C
\" " \"`
```

7.2 String Variables

`char *s = "Hello, world!"`. Is the same as `char s[] = "Hello, world!`. This is because `char *s` and `char s[]` as the same as both are just pointers to the first element in contiguous section of memory. 