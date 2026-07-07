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


