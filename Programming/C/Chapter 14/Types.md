![[Pasted image 20260707132813.png]]
`short` is the 16 bit integer
`long` is the 32 bit integer
`int` is also the 32 bit integer
`long long` is 64 bit integer

The header file `<limits.h>` defines macros that hold the ranges for various types. They look something like this:
![[Pasted image 20260707133334.png]]

The `char` type is signed by default. The maximum value of `char` is 127 and the minimum is `-128`. For an unsigned char it is 255

For all unsigned values the maximum value will always be $2^{x}-1$, where $x$ is the number of bits. 


