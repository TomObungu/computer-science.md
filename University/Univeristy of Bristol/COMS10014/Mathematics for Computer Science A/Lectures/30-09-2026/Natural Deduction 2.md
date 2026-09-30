 Consider the statement: When is $\phi \lor \psi$ true?
 In this case:
	 Either $\phi$ is true
	 Or $\psi$ is true. 
The introduction rule for disjunction is:
	Prove $p \lor \psi$
		Either prove $p$ or prove $\psi$


# Disjunction
## Introduction Form
Consider the case of introduction for disjunction. 
Claim $p\implies p \lor q$
Proof:
	1. Assume p
	2. $p\lor q$ $\implies$by introduction on 1
	3. $p\implies p \lor q$ $\implies$ introduction on 1,2

## Elimination Form
Consider the case of Elimination for disjunction. If we have $\phi \lor \psi$. Remember that elimination is true if we we have $\phi$. 
If we have $\phi \lor \rho$
	Assume $\phi$ and show $\rho$ follows 
	Assume $\psi$ and show $\rho$ follows
Conclude $\rho$ follows. 
The variable $\rho$ is the goal case 

## Example 
Claim $(p \lor q)\implies(q \lor p)$
Proof:
1	 Assume $p\lor q$. The goal or $\rho$ is $(q \lor p)$
2		Assume $p$
3		    $q\lor p$ by $\lor$ introduction on $2.$
4	 Assume $q$
5	  $q \lor p$ by $\lor$ introduction on 4
6   $q \lor p$ by $\lor$ elimination on 1,3,5

# Negation
The statement for negation is equivalent to  $¬\phi \equiv \phi \implies \bot$

Showing a statement is false is showing if a statement were true. Then false would follow. It is possible to do this using contradiction. 

## Introduction Form
Assume $\phi$ and show $\bot$
	Then we have $¬\phi$
However if $\bot$ is shown then that is a contradiction 

# Elimination 
If $¬\phi$ and $\phi$
	Then we can conclude $\bot$

Claim. $p\implies ¬¬p$
1. Assume $p$. The object is now to show $¬¬p$. Think about any introduction or elimination rules that can be used on any compound statement.  
	1. Assume $¬p$. For this statement 
	2. However this is a contradiction to $p\implies \bot$. $\implies$  $¬$elimination on 1,2

# Proving $\bot$ from Introduction
How would it be possible to prove $\bot$? 
The statement of $\bot$ only comes from contradictory assumptions. (¬Elimination)

Now consider the statement for $\bot$. If we have $\bot$ then $\phi$. This is due to vacuous truth. 

Claim: $(p \land ¬p) \implies q$. 

1. Assume $p \land ¬p$ 
2. $p$. Due to $\wedge$ elimination on $1$
3. $¬p$. Due to $\wedge$ elimination on 1
4. $\bot$ . Due to $¬$ elimination on 2
5. $q$ due to $\bot$ elimination on 
