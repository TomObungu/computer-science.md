# Counting number of bits using GCC __builtin

Using ``__builtin_popcount(n)`` will return the number of 1s in the binary representation of some number $n$.

Using ``__builtin_ctz(n)``  will return the trailing zeros in the the binary representation of some number $n$ and likewise ``__builtin_clz(n)`` will return the leading zeros. We can get the lowest/highest bit by doing $6$
 