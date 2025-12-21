# Counting number of bits using GCC __builtin


https://www.topcoder.com/thrive/articles/A%20bit%20of%20fun:%20fun%20with%20bits

Using ``__builtin_popcount(n)`` will return the number of 1s in the binary representation of some number $n$.

Using ``__builtin_ctz(n)``  will return the trailing zeros in the the binary representation of some number $n$ and likewise ``__builtin_clz(n)`` will return the leading zeros. 

We can get the highest bit by doing 32 - ``__builtin_ctz(n)`` if using ``unsgined int`` likewise if using `unsigned long long` we use do 64 and so on.  

If ``__builtin_clz(n)`` returns something like 4, then the lowest bit is the 4th bit from the right and so on.

How it is possible to do the same thing with `std::bitset`. 
```C++
bitset<8>(5).count
```

Popcount yields just the same asm output on latest g++. However, `__builtin_popcount` is an gcc extension and won't be available on neither other compilers nor other architectures than x86. Therefore, bitset option is clearly option.
## Example
```C++
// C++ code to demonstrate the
// __builtin_popcount function
#include <bits/stdc++.h>

using namespace std;

int main()
{

    long long n = 1e15;

    // Printing the number of set bits in n
    cout << __builtin_popcountll(n);

    return 0;
}
```
Output:
```
20
```

## Intersections of workers days problem

https://youtu.be/jqJ5s077OKo?si=RZkeD_tbLagV1IhS&t=113

There are $N\leq 5000$ workers. Each is available during some days of the month. Find two workers with maximum intersection of their schedules

Let's say you are given the schedules of the days that the workers are working during the month like this:
![[Pasted image 20251221223634.png]]

It is possible to solve this problem by representing the month as a bitset of length 30 and the days the worker is working as 1 in. E.g. for the first schedule:
$$
\{2,3,5,6,8\}
$$
The binary representation of the days 