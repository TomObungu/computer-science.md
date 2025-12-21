If you are given $N$ numbers, check if there is a subset of them such that sum of that subset is equal to some target value $S$. This is for the case when you cannot take each element more than once.
# Method 1 : using bit masks
https://youtu.be/xXKL9YBWgCY?si=l1zlpgPimmhsEEGi&t=556

This method is effective for when $N\leq 20$. 

This algorithm works by using a bit mask of $x$ where $1\leq  x \leq 2^{N}$. For each bit mask, the algorithm compares each bit and checks if the bit in that position is $1$. 

We iterate from mask $0$ to  $2^{N}$ as this considers $2^{N}$ different values, which is every possible mask, which is every possible subset.

The number of bits will be $N$. That is if we have a subset of length $8$, then we will compare each of the 8 bits of the bitset mask and check if it is 1 by using the bitwise $\&$ operation. If the bit in that position of that mask is 1 then we add it to a sum of the subset variable.

## What this represents:
Below is a visual representation of what is happening when iterating over each bit mask. We iterate over possible binary representation of the indices of the subset. For each possible binary representation, each index that is 1, we add that value at that index to the sum. 

Since there are $2^N$ different binary representations, each different binary representation represents the combinations of numbers from the given subset that can be summed together. 
![[Pasted image 20251221213246.png]]

We use this solve the subs


