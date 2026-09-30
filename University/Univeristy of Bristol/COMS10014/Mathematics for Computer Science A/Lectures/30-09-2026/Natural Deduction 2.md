 Consider the statement: When is $\phi \lor \psi$ true?
 In this case:
	 Either $\phi$ is true
	 Or $\psi$ is true. 
The introduction rule for disjunction is:
	Prove $p \lor \psi$
		Eitehr prove $p$ or prove $\psi$

# Introduction Form
Consider the case of introduction for disjunction. 
Claim $p\implies p \lor q$
Proof:
	1. Assume p
	2. $p\lor q$ $\implies$by introduction on 1
	3. $p\implies p \lor q$ $\implies$ introduction on 1,2

# Elimination Form
Consider the case of Elimination for disjunction. If we have $\phi \lor \psi$. Remember that elimination is true if we we have $\phi$. 
If we have $\phi \lor \rho$
	Assume $\phi$ and show $\rho$ follows 
	Assume $\psi$ and show $\rho$ follows
Conclude $\rho$ follows. 
The variable $\rho$ is the goal case 

# Example 
Claim $(p \lor q)\implies(q \lor p)$
Proof:
	1. Assume $p\lor q$. The goal or $\rho$ is $(q \lor p)$
	2. 