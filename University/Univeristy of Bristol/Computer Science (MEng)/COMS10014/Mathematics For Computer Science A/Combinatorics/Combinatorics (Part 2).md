# Permuation
A permuation is a the number of ways to select an ordered set of $k$ elements from $n$ elements with no repetition
$$
P(n,k) = \frac{n!}{(n-k)!}
$$
# Combination
A combination of $k$ elements from an $n$-element set is an unordered selection. The number of combinations is. That is, how many different combinations can you get from choose $k$ elements from a set of $n$.
$$
\begin{pmatrix}
n \\
k
\end{pmatrix} = \frac{n!}{k!(n-k)!}
$$

It is possible to show that $\begin{pmatrix} n \\ k\end{pmatrix} = \begin{pmatrix}n \\ n-k\end{pmatrix}$ due to symmetry 

Example : Consider 4 people A, B, C and D. How many 2-person committees can we form? 

Example : A project team of 4 is chosen from a class of 20. How many possible teams are there? 

$$
\begin{pmatrix}
20 \\
4
\end{pmatrix} = \frac{20!}{4!16!} = 190
$$

Example : A hand of 5 cars, how many ways can you choose 2 cars
$$
\begin{pmatrix}
5 \\
2
\end{pmatrix} = \frac{5!}{2!3!} = 10
$$

# Combinations vs. Permuations
When dealing with permutations, ordering matters. For example if you had a student committee and you wanted to pick a president, secretary, and treasurer, since these roles are distinct. Thus you would use permutations

Example : A standard 52-card deck has 4 suits and 13 ranks. The total 5-card hands are $\begin{pmatrix}52 \\ 2\end{pmatrix}$.

To choose the rank for the four there are 13 ways.  If all 4 suits are fixed, then you can choose the other 48 cards. This gives a total of $13 \times 48 = 624$ cards. 

Example : What would be the case of choosing three cards of one rank with the other two being different. 

You choose the rank for the three out of cards; there are 13 ways thus $13 \times\begin{pmatrix} 4  \\ 3\end{pmatrix}$. Then you choose the rank of the other 2 cards out of the 12 other rnaks, thus $\begin{pmatrix}12 \\ 2\end{pmatrix}$. You then choose the suit for each remaining card 

# Binomial Coefficients / Bionmial Expansion
For all intergers $n \geq 0$
$$
(x+y)^{n} = \sum_{k=0}^{n} \begin{pmatrix}
n \\
k
\end{pmatrix}x^{n-k}y^{k}
$$

For natural numbers with $n$ and $k$ with $1 \leq k \leq n$, Pascal's Identity holds:
$$
\begin{pmatrix}
n \\
k
\end{pmatrix} = \begin{pmatrix}
n - 1 \\
k - 1
\end{pmatrix} + \begin{pmatrix}
n - 1  \\
k
\end{pmatrix}
$$

# Counting Subsets
Each subset of$n$-element set corresponds to a binary string of length $n$:$2^{n}$
thus
$$
\sum_{k=0}^{n} \begin{pmatrix}
 n \\
k
\end{pmatrix} = 2^{n}
$$
To pick $k$ elements to include to include $n-k$ by symmetry:
$$
\begin{pmatrix}
n \\
k
\end{pmatrix} = \begin{pmatrix}
n \\
n - k
\end{pmatrix}
$$

# Multinomials
Recall $\begin{pmatrix} n \\ k\end{pmatrix}$ counts ways to split $n$ items into one group of $k$ and one group of $n-k$. What if we want three groups of sizes $k_{1}$, $k_{2}$ and $k_{3}$ with $k_{1}+k_{2}+k_{3} = n$?

1. Choose $k_{1}$ items from group 1: $\begin{pmatrix}n \\ k_{1}\end{pmatrix}$ ways. 
2. From what's left $(n-k_{1})$ choose $k_{2}$ from group 2: $\begin{pmatrix}n-k_{1} \\ k_{2}\end{pmatrix}$
3. For the remaining $k_{3} = n -k_{1} -k_{2}$ elements, there is only one way to choose an element. 

Thus gives the unified expression:
$$
\begin{pmatrix}
n \\
k_{1}
\end{pmatrix}\begin{pmatrix}
n-k_{1} \\
k_{2}
\end{pmatrix} = \frac{n!}{k_{1}!(n - k_{1})!} \frac{(n-k_{1})!}{k_{2}!(n-k_{1}-k_{2}!)} = \frac{n!}{k_{1}!k_{2}!k_{3}!}
$$

# Inclusion-Exclusion Principle
## Partitioning
If a set is split into disjoint parks, we can add their sizes directly
$$
| A \cup B | = | A \setminus B | + | B \setminus A | = | A \cap B |
$$
However, this is not the most natural way to split the elements. The Inclusion-Exclusion principle states:
$$
|A \cup B| = |A| + |B| - |A \cap B|
$$
The same holds for multiple sets, in that you remove the intersection for each individual set
$$
|A \cup B \cup C | = |A| + |B| + |C| = |A \cap B| - |A \cap C| - |B \cap C| + |A \cap B \cap C |
$$