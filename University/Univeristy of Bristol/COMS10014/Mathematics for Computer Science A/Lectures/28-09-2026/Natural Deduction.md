# Proofs
Consider a tautology below such as:
$$
\begin{gather*}
\phi \equiv \top \\ \\
\end{gather*}
$$
And:
$$
x > 0 \implies x > 1
$$
However with these tautologies, there are infinitely many cases. 

Proofs are there to follow steps to move what is known to what is proven. They are a way of demonstrating truth. 

Consider a formal proof such as:
$$
\begin{gather*}
2(x+3) -6 = 2x \\ \\
2x + 6 -6 = 2x \\ \\
2x = 2x \\ \\
x = x

\end{gather*}
$$

# Formal proofs vs. Informal Proof.
Informal proofs may have ambiguity and underlying assumptions. Thus forms of formal proof such as natural deduction are taken into account. Propositions are taken as evidence and proofs are taken to provide evidence. 

The steps to a formal proof can be broken down into logical steps:
1. Introductory steps
2. Eliminiation steps

Let's take a use of these steps to prove the implication rule
# Introduction
Consider the case of $\phi \implies \psi$. To prove $\phi \implies \psi$. Assume that $\phi$ is true. The goal is to prove $\psi$

Let's take the case of $x > 0  \implies x>1$. We start of by assuming $x>0$ and the goal in mind becomes proving $x>1$.
# Elimination 
If we have $\phi\implies \psi$ and we have $\phi$ then $\psi$ is true. The statement to 'have' means that $\phi$ is true or that $\phi$ has been proven. This means the basis of elimination starts from a true statement. 

Consider the case of $((p\implies p)\implies q)\implies q$.  We start of by assuming that $((p\implies p)\implies q)$.

The goal the becomes proving $q$. However within this assumption there is an implication of $(p \implies p)$. Thus we have a secondary sub-goal which is to show $(p\implies p)$. 

However this implication also has it's own assumption of $p$. This makes another sub-goal of $p$. 

If we were to use Elimination for the statement of $x > 0 \implies x +1$


