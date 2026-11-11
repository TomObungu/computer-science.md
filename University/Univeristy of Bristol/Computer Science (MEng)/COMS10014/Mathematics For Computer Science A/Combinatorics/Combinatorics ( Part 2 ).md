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

To choose the rank for the four there are 13 ways.  If all 4 suits are fixed, then you can choose 




