# General Purpose Derivation 
It is possible to take the abstract representation of truth tables in computation and produce a Boolean algebra statement or better, even a physical implementation of the representation in terms of semiconductors and transistors. 
# Algorithm 
It is possible to implement the Boolean expression $e$ from a truth table. The truth table contains some Boolean function with $n$ inputs and 1 output. 

Below is the rather overformalised algorithm for 

1. First let $T_{j}$ be synonmous for the $j$-th input within the table colum and  $O$ be a synonym for the output on the column. 
2. For each for in the truth table $i$ such that $i \in T$, for a term by AND'ing together the all inputs with the rules:
	1. If $T_{i}=0$  we use $I_{i}$
	2. If $Ti=0$ we use $¬I_{i}$
3. An expression i
