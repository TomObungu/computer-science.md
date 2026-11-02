You can do proof without induction, then that is usually simpler. You can use direct proofs to prove something like $n^{2}+n$ is even. However for other cases like the sum of natural numbers, $1+\dots+n +\frac{n^{2}+n}{2}$, then induction is the right tool to use. 

Induction Comes in at least two forms:
	1. Induction over the natural numbers
	2. Structural induction 

# Induction over the Natural Numbers
Consider a statement like Gauss's formula:
$$
\begin{gather*}
1 + 2 + \dots + n = \frac{n(n+1)}{2} \\ \\
\sum_{i=1}^{n}i = \frac{n(n+1)}{2}
\end{gather*}
$$
To prove a statement like this is to split the proof into two steps. 
1. Prove the base case $S(0)$
2. Prove  the induction step $S(n)\to S(n+1)$ leaving $n$ as free variable

If you want to prove holds for all natural numbers $n \geq k$ for some $k$. Then change the base case to showing $S(k)$. 

# Statements of the form $L(n)=R(n)$
If we are proving a statement of the form $L(n) = R(n)$ we can use a template:
1. Define $L(n)$ and $R(n)$ 
2. State the base case to of $n=0$. Ca