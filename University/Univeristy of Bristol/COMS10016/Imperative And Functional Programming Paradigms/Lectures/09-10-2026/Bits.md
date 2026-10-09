"\[In coding\] the wages of sin is debugging" - Ron Jeffries 
# Binary Integer Representation
Usually it is possible to represent unsigned positive integers in decimal notation. Decimal notation is in base 10. 
$$
137_{10} = 0 *10^{3} + 1 * 10^{2} + 3*10^{1} + 7 * 10^{0}
$$
A binary representation of integers follows the same scheme but using base 2 and digits ranging from 0 to 1. For example the binary digit `1110_2` is represented as:
$$
1110_{2} = 0 * 2^{4} +1 * 2^{3} + 1 * 2^{2}+ 1 * 2^{1} + 0 * 2^{2}
$$

# Fixed Length Binary Representation
Consider the fact that there is a fixed an limit number of bits available to represent an unsigned integer within memory. For example, if we have 8 bits available for an unsigned integer, this is identical to `unsigned char`. 
One Byte covers a range from 0 to 255. Not 256 as 0 itself is considered as number. 

# Nibbles and C Hex Representation 
The four bits of a Nibble represent 16 different states ranging form 0 to 15. A single hexadecimal digit of base 16 compactly represents one Nibble e.g.:
$$
1110_{}{2} = 14_{10} = E_{16}
$$
In, hex literals in C start with `0x` in front. For example to encode the 8 bit number `0000 1110` as below. This binary digit contains 2 Nibbles or 1 byte.
```c
unsigned char byte = 0x0E // 0000 1110
```

A unsigned short in 16 bits or 2 bytes may  be represented as 4 Nibbles or 4 hex digits.
```C
unsigned short word = 0x010E;
```

# Overflow
Incrementing unsigned integer beyond the representation limit, it will overflow and wrap round to to the smallest number
```C
unsigned char byte = 0xFF
byte++; // overflow, byte is now 0
```
The same occurs for an underflow
```C
unsigned char byte = 0x00
byte--; // underflow, byte is now 255
```

# Two's Complement Representation
To convert a positive binary number to it's negative two's complement equivalent, you must flip every bit and add 1. 
```
127 = 01111111
	= 10000000 + 00000001 = 10000001 = -127
```
For signed chars, the leftmost bit is reserved for the sign. 
```C
signed char signedByte = 127; // holding 0111 11
```
Each every signed integer with $n$ bits it's limits are:
$$
-2^{n-1} - 2^{n-1} - 1
$$
# Printing Hex in Representation
```C
unsigned char byte = 0x0E;
printf("%02x\n", byte);
// prints 0x0e
```

# Coercion, Truncation, Sign Extension
When different types are combined without casts, there are implicit rules of conversion, called coercion. 

