# Product Rule
If a process decomposes into two independent stages, with $a$ possible outcomes for stage 1 and $b$ outcomes for stage 2, then the total number of possible outcomes  $a \times b$

For example a 2 character ID has 10 choices for a digit and 26 choices for a letter, thus the total choices are $10 \times 26$

Thus in general for a function 

The special case for binary functions $A \to \{0,1\}$ the total outcome is $2^{|A|}$.

Independence is essential for multiplication in the product rule. You can only use this if the taking a choice does not alter the range of outcomes. 

# Sum Rule
If a task can be accompanied in one of two disjoint ways, with $a$ outcomes and $b$ outcomes, then the total number of options is $a+b$.

Consider building a user name of length 3 made entirely of digits or entirely letters will be $10^{3} + 26^{3}$. 

This is because the product rule for entirely will be $10\times 10 \times 10$ and for letters $26 \times 26 \times 26$. 

If there is overlap in counting then you must over count and subtract the intersection between sets
$$
|A| + |B| - |A \cap B|
$$

# Factorial and basic permutations
It is possible to arrange $n$ distinct items in order in $n!$ ways. 

## Choosing and arranging a subset
For example if you want to choose 2 books out of 3 book to arrange, then number of possible arrangements is. Thus, to arrange $m$ out of $n$ distinct items:
$$
P(n,m) = \frac{n!}{(n-m)!}
$$
Example : How many 3-place prize orders can be awarded among 12 medallists?
Answer $\frac{12!}{(12-3)!}=\frac{12!}{9!}=1320$. 

# Permutations with repetition
For a multi set with total $n$ elements, where $n_{i}$ are the counts of each distinct symbol
$$
N = \frac{n!}{n_{1}!n_{2}!\dots n_{k}!}
$$
Example : How many permutations are there of the word BALLOON. Since L appears twice. This is because when dealing with the same letters, swapping positions of the same letters will yield an unchanged result. This is why we can divide it:
$$
\frac{7!}{2!2!}
$$
Example how many permutations of the word MISSISSIPPI, S repeats 4 times, I repeats 4 times and p 2 times. 
$$
\frac{11!}{4!4!2!}
$$

# 