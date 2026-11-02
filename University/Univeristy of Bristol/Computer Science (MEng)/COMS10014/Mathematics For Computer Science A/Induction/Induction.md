You can do proof without induction, then that is usually simpler. You can use direct proofs to prove something like $n^{2}+n$ is even. However for other cases like the sum of natural numbers, $1+\dots+n +\frac{n^{2}+n}{2}$, then induction is the right tool to use. 

Induction Comes in at least two forms:
	1. Induction over the natural numbers
	2. Structural induction 

---
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

---
# Statements of the form $L(n)=R(n)$
If we are proving a statement of the form $L(n) = R(n)$ we can use a template:
1. Define $L(n)$ and $R(n)$ 
2. State the base case of $n=0$. Calculate $L(0)$ and $R(0)$. Check that they are the same. Start with $k$ if the statement holds for $n \geq k$
3. State "Induction step, assuming $L(k) = R(k)$ holds, we want to show $L(k+1) = R(k+1)$". In this case you can use $n$ as a variable or use some other variable like $k$
4. Write out $L(k+1)$ and calculate
5. At some point you will have a subterm $L(n)$ say "Using the induction assumption", replace it with $R(n)$
6. Continue calculating until you hopefully have $R(k+1)$
# Example


---
# Well Ordering 
Why does induction work? Or better, when does induction work?

The claim is suppose that $S(n)$ is a proposition with variable $n$ and that $S(0)$ is true and $S(n)\to S(n+1)$ is a tautology. Then for every $x \in \mathbb{N}$, $S(x)$ is true. 

We can prove this statement by contradiction. Suppose that this is not the case. That there is some natural number $x$ for which $S(x)$ is not true. Let $x$ be the smallest such number $x$.

1. If $x=0$ then $S(0)$ is false, but this is a contradiction the assumption $S(0)$ is true.
2. If $x >0$, then $x-1$ is also a natural number. Since $x$ was the smallest natural number where $S$ not true then $S(x-1)$ must be true. However, setting $S(n)$ for $n=x-1$ we get that $S(x)$ is true, however this is a contradiction 


---
# Structural Induction
---

## Well-Ordering for Structural Induction
