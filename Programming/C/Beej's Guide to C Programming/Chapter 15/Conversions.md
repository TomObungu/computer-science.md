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

