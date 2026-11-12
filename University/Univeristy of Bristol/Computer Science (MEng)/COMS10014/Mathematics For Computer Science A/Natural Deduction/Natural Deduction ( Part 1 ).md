Natural deduction is a form of formal proof. Whenever we set out to prove something, we work with a goal and set of assumptions trying to be proved. 

An assumption isn't a claim that a proposition is true, but rather it is a condition under which we are asserting that the goal follows. For example, under the assumption $x > 1$, we have that $x^{2}>x$, we are not asserting $x >1$ is true, we are merely narrowing the scope of when $x^{2}>x$ should apply

# Proof Rules
For each Boolean connective there are two types of proof steps
- Introduction rules constructs the information 
- Elimination extracts the information inside a proposition i.e once we have proven it or have it as assumption, we use it to prove something else

# Definition for $\implies$
For any propositions $\phi$ and $\psi$, 
	- ($\implies$ introduction) To prove $\phi \implies \psi$, assume $\phi$ and then prove $\psi$
	- ($\implies$ elimination)  if we have $\phi\implies \psi$, and $\phi$ we we may conclude $\psi$

E.g. if you have the assumption $(p\implies p) \implies q$. If we have $(p\implies p)$ then we can conclude $p$. The 

# Example 1
Claim. $((p\implies p)\implies q)\implies q$. For nested implication proofs like this, you can use a tree to split it up into the middle most connective. Often we dealing with proofs, start with the left most antcedent
![[Pasted image 20261112074754.png]]

1. Assume $(p\implies p)\implies q$.The goal is $q$
2. Using a tree to split the implication up even more, our goal becomes $p\implies p$
3. Splitting up again, we assume $p$. 
4. If we have $p$, we have $p\implies p$ by $\implies$ introduction
5. If we have $p\implies p$  we have $q$ by $\implies$ elimination 
6. We have $q$, thus we now have $((p\implies p)\implies q)\implies q$ by $\implies$ introduction
$$
\square
$$

# Definition for $\wedge$
For any propositions $\phi$ and $\psi$
- ($\wedge$ introduction). To prove $\phi \wedge \psi$, prove both $\phi$ and$\psi$
-  ($\wedge$ elimination). If we have $\phi \land \psi$. Then we may conclude $\psi$ and $\psi$

# Example 2
Claim. $p\implies q\implies p \wedge q$
1. Assume $p \wedge q$, 
2. 