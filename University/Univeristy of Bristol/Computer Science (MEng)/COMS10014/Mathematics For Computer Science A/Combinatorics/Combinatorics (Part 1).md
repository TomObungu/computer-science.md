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

# Restricted Permutations
# Relative-order constraints
Consider the case of arranging the letters of Algorithm so that $A$ appears before $M$. All $9!$ permutation letters are equally likely, thus by symmetry: $\frac{9!}{2}$

# Adjacency constraint
If two specific elements must sit together, treat them as a block. 

Example : . 8 students line up and two particular students must sit together. There are $7!$ways to arrange the blocks and $2!$ to arrange the pair internally:
$$
7! \times 2!
$$
# Circular Constraints
To arrange $n$ people around a table, the number of permutations is:
$$
(n-1)!
$$
This is because on a table, there are $n$ repeated counts for rotations, thus consider those counts you must do $\frac{n!}{n}$.

Example : If two particular people must sit together, treat them as a block, seat the $n-1$ objects around the table to array the pair internally
$$
(n-2)! \times 2
$$


