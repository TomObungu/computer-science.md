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

Void pointers indi