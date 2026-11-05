
For some $\hat{x} \mapsto x$ and $\hat{y} \mapsto y$, it is possible to computer $\hat{r} \mapsto r =x \times y$. Where $r$ produces a $2\cdot n$ product. In this case $\hat{y}$ is called the multiplier and $\hat{x}$ is the multiplicand. 
$$
f : {0,1}^{n} \times {0, 1}^{n} \to {0,1}^{2 \cdot n}
$$
# Operand Scanning
The multiplication using tables that is commonly known is known as operand scanning. Consider $y$ and $x$; An algorithm for such would step through the digits of$y_{i}$ and out loop steps through $\xi$

# Product Scanning
We know that $r$ will be of $2\cdot n$ thus for every bit column $r_{k}$, the corresponding $x$
# Horner's Rule
It is similar to binary exponentiation in that when evaluating $y\times x$. The product is computed by multiplying $y_{i}$ by $x$ and by $2^{i}$ where $i$ is the position of the bit and adding the next $i$ bit position. Thus to comput $y\times x$ where $y$ is an expression with $n$ bits in base $2$. 
$$
y \times x = y_{0} \cdot x  + 2 \cdot ( y_{1} \cdot x + 2 \cdot (y_{2}  \cdot x \dots + 2(y_{n-1} \cdot x))
$$

## Combinatorical Approach
It is possible to compute $r$ via AND gates to generate partial results. Some left-shift components  e.g. wires shifting, computation or multiplexers and some adder components to sums the scaled partial sums. 
![[Pasted image 20261105114800.png]]

The positive side of this is that it requires a larger data-path. Requires no control path. As this is a combinatorical circuit, it requires only one step.

## Sequential Approach

