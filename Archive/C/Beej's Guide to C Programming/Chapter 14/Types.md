![[Pasted image 20260707132813.png]]
`short` is the 16 bit integer
`long` must be at least 32 bit integer
In many systems `int` is 32 bits, but the difference between long and int is that it has to at least be 16 bits
`long long` is 64 bit integer

In some systems like macOS, long is larger than int `int` at 64 bits. 

The header file `<limits.h>` defines macros that hold the ranges for various types. They look something like this:
![[Pasted image 20260707133334.png]]
![[Pasted image 20260707133638.png]]


The `char` type is signed by default. The maximum value of `char` is 127 and the minimum is `-128`. For an unsigned char it is 255

For all unsigned values the maximum value will always be $2^{x}-1$, where $x$ is the number of bits. 

# 14.4 More Float : double and long double

We can find out the bits  of precision allocated for the floating point decimal types in `<float.h>`

The number of decimal digits that stored in each type are given by these macros:

![[Pasted image 20260707134131.png]]

It varies system by system but the number of bytes of precision can be represented using `sizeof`

![[Pasted image 20260708083228.png]]


In the `<float.h>` header, you can find out the number of decimal digits encoded in a float with these macros

![[Pasted image 20260708083355.png]]

When using these floats, going past the defined limit will cause things to start to go wrong. 

You can define the number of significant figures by putting `.11` next to the type specifier when printing
```C
printf("%.11f\n", f);
```

It is possible to write hex digits like this C
```C
int a = 0x1A2B
```
printing this number will yield a hex number

Padding a number `0` like this will cause the number to be treated as an octal number:
```C
int a = 012
```

## Integer Constants and suffixes

![[Pasted image 20260707134742.png]]


When dealing with integers use 

# Exponent notation
It is possible to write exponent notation using `-` or `+`. For example if you want to write 0.000123 in a `double` you do
```C
double x = 1.2345-3
```
If you want to write 100 trillion you do 
```C
long long x = 1.0+14
```
You could also use `e` instead of `+`

## Hexadecimal floating point constants

All hexadecimal numbers begin with a `0x` just like integer numbers. 

However you must specify the exponent with `p`. For example the hex number below
```C
double x = 0xa.1p3;
```
