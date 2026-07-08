To convert a number to a string use `snprintf`

It works like `printf` but instead it prints the out to a string variable. 

```C
int main(void)
{
	char s[10];
	float f = 3.14159
	
	snprinf(s, 10, "%f", f)
	printf("%s", s)
}
```

For basic conversion from string to a number try the `atoi` functions from `stdlib.h`

`atoi` - string to int
`atof` - string to float
`atol` - string to long int
`atoll` - string to long long int

```C
int main(void)
{
	char *pi = 3.14159;
	float f;
	
	f = atof(pi);
	
	printf("%f\n",f);
}

```

However passing strings to functions produces undefined behaviour

```C
int x = atoi("what") // undefined behaviour
```
For better error handling, use the `strtol` functions also in `stdlib.h`. These functions convert more types aswell

`strtol` - string to long int
`strtoll` - string to long long int
`strtoul` - string to unsigned long int
`strtoull` - string to unsigned long long int
``strtof - string to float
`strtof` - string to double
`strtold` - string to long double 