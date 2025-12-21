# Counting number of bits using GCC __builtin


https://www.topcoder.com/thrive/articles/A%20bit%20of%20fun:%20fun%20with%20bits

Using ``__builtin_popcount(n)`` will return the number of 1s in the binary representation of some number $n$.

Using ``__builtin_ctz(n)``  will return the trailing zeros in the the binary representation of some number $n$ and likewise ``__builtin_clz(n)`` will return the leading zeros. 

We can get the highest bit by doing 32 - ``__builtin_ctz(n)`` if using ``unsgined int`` likewise if using `unsigned long long` we use do 64 and so on.  

If ``__builtin_clz(n)`` returns something like 4, then the lowest bit is the 4th bit from the right and so on.

