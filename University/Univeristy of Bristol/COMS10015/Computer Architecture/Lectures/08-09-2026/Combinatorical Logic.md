# General Purpose Derivation 
It is possible to take the abstract representation of truth tables in computation and produce a Boolean algebra statement or better, even a physical implementation of the representation in terms of semiconductors and transistors. 
# Method 1: Computational Algorithm 
It is possible to implement the Boolean expression $e$ from a truth table. The truth table contains some Boolean function with $n$ inputs and 1 output. 

Below is the rather over-formalised algorithm for this computational approach.

1. First let $I_{j}$ be synonymous for the $j$-th input within the table column and  $O$ be a synonym for the output on the column. 
2. For each element  for in the truth table $i$ such that $i \in T$, for a term $t_{i}$ by AND'ing together the all inputs with the rules:
	1. If $I_{i}=0$  we use $I_{i}$
	2. If $I_{j}=0$ we use $¬I_{i}$
3. An expression implementing the function is then formed by OR'ing together all the terms, i.e. 
$$
\begin{gather*}
e = \bigvee_{{i \in T}} t_{i} \\ \\
\end{gather*}
$$
The following output gives a result in Sum Of Products (SoP) form. 

# Method 2 : Karnaugh Maps
A different approach is to use a Karnaugh map. Karnaugh maps may be useful when dealing with truth tables with more binary rows.  The truth table contains $n$ inputs and 1 output. The result of using a Karnaugh map will produce a Boolean expression $e$ that implements $f$.

Below is the formal explanation of the approach to use a Karnaugh map.

1. Draw a rectangular $p\times q$ -element grid, such that
	1. $p\equiv q\equiv 0$
	2. $p \cdot q = 2^{n}$
2. Fill the grid elements with the output corresponding to inputs for that row and colum
3. Cover rectangular groups of adjacent 1 elements which are of total size $2^{m}$ for some $m$. 
	1. Ensure that the groups are largest value of $2^{m}$ as possible
	2. With the above premises ensure that there are fewer groups
4. Translate each group into one term of an SoP form Boolean expression.

## Example
