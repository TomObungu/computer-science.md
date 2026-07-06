# Pointer Arithmetic
You can increment from a pointer like this. It is useful for arrays. This does not modify the value of the pointer
```C
int a[5] = {11, 22, 33, 44, 55};
int *p = &a[0]; // Or "int *p = a;" works just as well
for (int i = 0; i < 5; i++) {
printf("%d\n", *(p + i)); // Same as p[i]!
}
```

In pointer arithmetic 

```
E1[E2] is identical to (*((E1)+(E2)))
```
