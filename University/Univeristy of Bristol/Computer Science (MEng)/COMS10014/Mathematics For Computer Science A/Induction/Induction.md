You can do proof without induction, then that is usually simpler. You can use direct proofs to prove something like $n^{2}+n$ is even. However for other cases like the sum of natural numbers, $1+\dots+n +\frac{n^{2}+n}{2}$, then induction is the right tool to use. 

Induction Comes in at least two forms:
	1. Induction over the natural numbers
	2. Strurctural induction 

# Induction over the Natural Numbers
Consider a statement like Gauss's formula:
$$
\begin{gather*}
1 + 2 + \dots + n = \frac{n(n+1)}{2} \\ \\
\sum_{i=1}^{n}i = \frac{n(n+1)}{2}
\end{gather*}
$$
To prove a statement like this is to split the proof into two steps. 