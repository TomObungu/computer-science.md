# 7.1 String Literals

You can represent strings like sentences using double quotation marks as string literals E.g. `"Hello, world!"`

In C you can put the quotation marks inside a string using:
```C
\" " \"`
```

# 7.2 String Variables

`char *s = "Hello, world!"`. Is the same as `char s[] = "Hello, world!`. This is because `char *s` and `char s[]` as the same as both are just pointers to the first element in contiguous section of memory.

However `char *s` is not mutable

```C
char *s = "Hello, world!";
printf("%s\n", s); // "Hello, world!"

```C
char s[] = "Hello, world!";
printf("%s\n", s); // "Hello, world!"
```

You can also pre-define the size of the array:
```C
char s[14] = "Hello, World!"
```

The string specifier for characters is `%c`:
``` C
int main(void) {
	char s[] = "Hello, world!";
	for (int i = 0; i < 13; i++)
		printf("%c", s[i]);
	printf("\n");
}
```





char t[] = "Hello, again!"; // t is an array copy of the string
t[0] = 'z'; // No problem
printf("%s\n", t); // "zello, again!