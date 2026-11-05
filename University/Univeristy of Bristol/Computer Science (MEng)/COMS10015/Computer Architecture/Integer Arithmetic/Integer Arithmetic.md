
For some $\hat{x} \mapsto x$ and $\hat{y} \mapsto y$, it is possible to computer $\hat{r} \mapsto r =x \times y$. Where $r$ produces a $2\cdot n$ product. In this case $\hat{y}$ is called the multiplier and $\hat{x}$ is the multiplicand. 
$$
f : {0,1}^{n} \times {0, 1}^{n} \to {0,1}^{2 \cdot n}
$$
# Operand Scanning
For integers $x$ and$y$, the multiplication using tables that is commonly known is known as operand scanning. In the inner loop $j=0$ up to $l_{y}$ and $j=0$ up to $l_{x}$, $y_{i}\times x_{j}$ is computed correspondingly. 
# Product Scanning
Similar to operand scanning in that you gain the same complexity, however the ordering of multiplication differs. 

We know that $r$ will be of $2\cdot n$ there is an outer loop  up to $r_{k}$. The crucial step is that to two inner loops that are up $j=0$ up to $l_{y}-1$ and $i=0$  $l_{x}-1$. If $i+j = k$, then $y_{i} \times x_{j}$ is computed. This is then added to the resulting sum. 
## Algorithm 
1. $l_{x} \gets |x|$, $l_{y} \gets |y|$, $l_{r} \gets  l_{x} + l_{y}$
2. $r \gets 0$, $c_{0} \gets 0$, $c_{2} \gets 0$
3. for $k=0$ upto $l_{x}+l_{y}$ step $+1$ do
	1. for $j=0$ upto $l_{x}+l_{y}$ step $+1$ do
		1. for $i=0$ upto $l_{y} -1$ step $+1$ do
			1. for $j=0$ upto $l_{y} -1$ step $+1$ do
				1. if $(j+i)=k$ then
					1. $u \cdot b + v = t \gets  y_{i} \cdot x_{i}$
					2. $c \dot{ b + c_{0}} = t \gets c_{0} + v$
					3. $c_{2} \gets c_{2} + c$
	2. $r_{k} \gets c_{0}, c_{0} \gets c_{1}, c_{1} \gets c_{2}, c_{2} \gets 0$
4. $r_{l_{x}+l_{y}-1} \gets 0$

# Additive multiplication
Multiplication means repeated addition, i.e
$$
y \times x = x + x \dots + x
$$
Expressing $y$ in base-2. We can see that 
$$
y \times x = \underbrace{ (y_{0}\cdot 2^{0} + y_{0}\cdot 2^{0} \dots y_{n-1}\cdot 2^{n-1}) + (y_{0}\cdot 2^{0} + y_{0}\cdot 2^{0} \dots y_{n-1}\cdot 2^{n-1}) \dots }_{ \text{x times} } 
$$
Where $y_{i}$ is the bit value of either 1 or 0. 
# Horner's Rule
For base 2 binary. It is similar to binary exponentiation in that when evaluating $y\times x$. The product is computed by multiplying $y_{i}$ by $x$ and by $2^{i}$ where $i$ is the position of the bit and adding the next $i$ bit position. Thus to comput $y\times x$ where $y$ is an expression with $n$ bits in base $2$. 
$$
\begin{gather*}
y \times x = y_{0} \cdot x  + 2 \cdot ( y_{1} \cdot x + 2 \cdot (y_{2}  \cdot x \dots + 2(y_{n-1} \cdot x)) \\ \\
\left(\sum ^{n-1}_{i=0} y_{i} \cdot 2^{i} \cdot x\right)
\end{gather*}
$$

Thus for ever intermediate step $r'$, it possible to specialise it as
$$
r_{i} \gets y_{i} \cdot x + 2 \cdot r_{i-1}
$$
This can be further specialised in form 
$$
r' \gets \begin{cases}
2\cdot r \equiv (r \ll 1), \text{ if} y_{i} =0\\ \\
x \cdot + 2 \cdot r \equiv x + ( r \ll 1), \\
  \text{ if} y_{i}=1
\end{cases} 
$$
## Combinatorical Approach
It is possible to compute $r$ via AND gates to generate partial results. Some left-shift components  e.g. wires shifting, computation or multiplexers and some adder components to sums the scaled partial sums. 
![[Pasted image 20261105114800.png]]

The positive side of this is that it requires a larger data-path. Requires no control path. As this is a combinatorical circuit, it requires only one step.

## Sequential Approach
It is possible to express $r_{i} \gets y_{i} \cdot x + 2 \cdot r_{i-1}$using sequential logic with the use of 
![[Pasted image 20261105220136.png]]