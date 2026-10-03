If you are given $N$ numbers, check if there is a subset of them such that sum of that subset is equal to some target value $S$. This is for the case when you cannot take each element more than once.
# Method 1 : using bit masks
https://youtu.be/xXKL9YBWgCY?si=l1zlpgPimmhsEEGi&t=556

This method is effective for when $N\leq 20$. 

This algorithm works by using a bitmask of $x$ where $0\leq  x \leq 2^{N}$. For each bit mask, the algorithm compares each bit and checks if the bit in that position is $1$. 

Even though $x$ itself is a number that ranges from $0\leq x\leq 2^{N}$, each bit mask is the binary representation of $x$. E.g when $x=0$, the bitmask will be $00000000$, when $x=1$, the bit mask will be $00000001$, $x=2$: $00000010$ and so on.

We iterate from mask $0$ to  $2^{N}$ as this considers $2^{N}$ different values, which is every possible mask, which is every possible subset.

The number of bits will be $N$. That is if we have a subset of length $N=8$, then we will compare each of the 8 bits with the bitmask $x$ and check if it is 1 by using the bitwise $\&$ operation. If the bit in that position of that mask is 1 then we add it to a sum of the subset variable.

## What this represents:
Below is a visual representation of what is happening when iterating over each bit mask. We iterate over possible binary representation of the indices of the subset.

For each possible binary representation, each bit that is 1 corresponds to an index of the subset. For example, for a subset of size $N=3$ representing a 3 bit binary number, if the most significant bit is 1 then this corresponds to index 0 of the subset. If the second most bit from the left is 1, then that corresponds to index 1 of the subset and so on.  we add that value at that index to the sum. 

Since there are $2^N$ different binary representations, each different binary representation represents the combinations of indexes from the given subset. For each index that is 1, we add that to the sum of that subset and compare.
![[Pasted image 20251221213246.png]]

We use this solve the subset mask problem by iterating over each subset and comparing check if that sum is equal to that target value $S$

## Code
![[Pasted image 20251221214735.png]]

```C++
for(int mask = 0; mask < (1 << n); mask++){
	long long sum_of_this_subset = 0;
	for(int i = 0; i < n; i++){
		if(mask & (1 << i)){ // Compare if bit at position i from the right is 1
			sum_of_this_subset +=a[i];
	}
	if(sum_of_this_subset == S){
		return "YES;
	}
}
return "NO";
```


Time complexity: $O(2^{N} \cdot N)$, where $N$ is the size of the subset. 

