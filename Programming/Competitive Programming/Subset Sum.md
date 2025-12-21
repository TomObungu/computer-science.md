If you are given $N$ numbers, check if there is a subset of them such that sum of that subset is equal to some target value $S$. This is for the case when you cannot take each element more than once.
# Method 1 : using bit masks
https://youtu.be/xXKL9YBWgCY?si=l1zlpgPimmhsEEGi&t=556

This method is effective for when $N\leq 20$. 

This algorithm works by using a bit mask of $x$ where $1\leq  x \leq N$. For each bit mask, the algorithm compares each bit and checks if the bit in that position is $1$. The number of bits will be $N$. That is if we have a subset of length $8$, then we will compare each of the 8 bits of the bitset mask and check if it is 1 by using the bitwise $\&$ operation. 