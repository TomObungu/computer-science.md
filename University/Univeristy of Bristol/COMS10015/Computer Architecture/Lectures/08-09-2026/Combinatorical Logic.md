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
The following output gives a result in Sum Of Positives form or SoP form. 

# Method 2 : Karnaugh Maps
A different approach is to use a Karnaugh map. Karnaugh maps may be useful when dealing with truth tables with more binary rows. 

Below is the formal explanation of the approach to use a Karnaugh map