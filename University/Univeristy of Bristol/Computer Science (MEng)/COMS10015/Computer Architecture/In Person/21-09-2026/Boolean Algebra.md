In set theory, for some set $x$ we have that $\phi$ denotes the empty set. Thus:
$$
\begin{gather*}
x \cup \phi = x \\ \\
\end{gather*}
$$
This takes the same form as elementary algebra, for some number $x$:
$$
\begin{gather*}
x + 0 = x \\ 
\end{gather*}
$$
In propositoinal logic, for some truth value $x$, we can see that:
$$
\begin{gather*}
x \wedge \text{true} = x \\ \\
x \lor \text{false} = x
\end{gather*}
$$

In Boolean algebra, you must:
	1. work with the set of binary digits. That is with $0$ or $1$. The set of binary digits can be denoted as:
$$
\mathbb{B} = \{0,1\}
$$
2. Shorten every statement into either a variable or a function
3. Use unary operators such as `¬` and binary operators $\wedge$`
4. Manipulate said expressions according to some axioms (or rules)

Then you must take the result into Boolean algebra. 



# Axioms
## Commutativity
$$
x \wedge y \equiv y  \wedge x
$$
## Association 
$$
 (x \wedge y) \wedge z \equiv x \wedge  (y\wedge z) 
$$
## Distribution
$$
x \wedge (y \lor z) \equiv (x \wedge y) \lor (x \wedge z)
$$

## Absorption
$$
x \wedge (x \lor y) \equiv x
$$
# De Morgan's law
$$
¬(x \wedge y) \equiv ¬x \lor y
$$

# Implication
Why does x=0 and y=0 in the logic statement of x => y evaluate to true? Will this is due to the the implication law. 
$$
x \implies y \equiv ¬x \lor y
$$


| $x$ | $y$ | $x \implies y$ |
| --- | --- | -------------- |


# NAND
The symbolic representation of NOT-AND is $\land$