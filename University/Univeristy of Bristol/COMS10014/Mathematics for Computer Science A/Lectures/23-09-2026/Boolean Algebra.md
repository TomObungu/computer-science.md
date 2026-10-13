# What is Algebra?
Algebra is about equality. When you consider the equation, the left hand must equal to the right hand side. As well as that there are two things founded within algebra, that is, syntax and semantics. The syntax of an algebraic equation is the symbolic representation whereas the semantics of  of an algebraic representation is the meaning.
$$
x + y = z
$$
For example take the equation below. It is true that the left hand side is equal to right hand side. They are not syntactically the same term, however they mean the same thing. 
$$
x + 0 = x
$$
Thus the equation below would yield the equivalence below:
$$
p \land \top \equiv p 
$$
This equation would be true for the corresponding truth table
$$
\begin{align}
\begin{array}{c|c}
\text{p}  & p \land \top \\
\hline 
\top  & \bot\\
\top   & \bot
\end{array}{} &\equiv \begin{array}{c|c} 
p  & p  \\
\hline 
\top  & \bot\\
\top   & \bot
\end{array}
\end{align}
$$
If we were to take an equation within Boolean Algebra, it is possible to show equality in the same manner:
$$
(p \wedge q )\lor r \equiv p \wedge q \lor r
$$
# Variables
Greek letters such as $\psi,\phi,\rho$ are variables that stand in for arbitrary proposition **formulas** themselves. Propositional formulas contain propositional variables plus a combination or operators such as conjunction, disjunction and negation. 

Letters $p$, $q$, and $r$ are variables used to represent variables in propositions that can take in values. 

Two propositional formulas are equivalent if they equal under all assignments. If $\phi$ and $\psi$ evaluate to the same truth value, regardless of the assignments of $p$, $q$ and $r$. 
# Associativity 
The associativity rule means that algebraic statements are true regardless of the placement of parenthesis. The equation below evaluates to true. If the individual truth tables were to be drawn out, comparing the truth tables will show the equivalence. This is the case for the conjunction.
$$
\begin{gather*}
(\phi \wedge \psi ) \lor \rho \equiv \phi \wedge (\psi \wedge \rho) \\ \\
(\phi \lor \psi ) \lor \rho \equiv \phi \lor ( \psi \lor \rho)
\end{gather*}
$$
# Commutativity
This means that the algebraic statements are true regardless of the ordering of the variables.
$$
\phi \wedge \psi \equiv \psi \wedge \phi
$$
# Distributitivity 
This means that the single statement on the left hand side of the equation can be further expanded into a fuller form containing the corresponding conjunctions and disjunctions. Below is the case for pushing a conjunction within a disjunction.
$$
\phi \wedge ( \psi \lor \rho) \equiv (\phi \wedge \psi) \lor (\phi \wedge \rho)
$$
Below is the case for pushing a disjunction within a conjunction:
$$
\phi \lor( \psi \wedge \rho) \equiv (\phi \lor \psi)\wedge (\phi \wedge \rho)
$$
This is very similar to the algebraic law of addition.
$$
(x + y) + z \equiv x + (y + z)
$$
# Idempotence
The definition of idempotent means that the algebraic expression is left unaffected if the terms are repeated. For example consider the expression below. 
$$
\begin{gather*}
\phi \wedge \phi \equiv \phi \\ \\
\phi \lor \phi \equiv \phi
\end{gather*}
$$

## The law of the excluded middle
This law means that a variable in disjunction with the negation of itself will always evaluate to true. For conjunctions, it impossible for of them to be true at the same otherwise there would be a contradiction.

This is because the that using the disjunction (OR) table with $\phi$ will always evaluate to true due to $\phi$ being true within itself.  
$$
\begin{gather*}
\phi \lor ¬\phi \equiv \top \\ \\
\phi \wedge ¬\phi \equiv \bot
\end{gather*} 
$$

# Tautology
A tautology is a proposition that is universally true regardless of the statement. That is the propositional formula statement below is true regardless.
$$
\phi \equiv \top
$$
Tautologies are the basic logical facts. They contain enough information within themselves for the statement to evaluate to true. 
### Valid 
A statement that is always true. For example the equation below is a valid claim:
$$
x > -100 \implies x > 0 
$$
### Invalid
A statement that is not always true. This does not necessarily mean that is always false.
$$
\phi \not\equiv \top 
$$
A statement such as
$$
x > 0
$$
Can be invalid as it is not always true for some arbitrarily given variable $x$. 
### Satisfiable 
A statement that **can** be true. A statement that is not always false. Below are satisfiable statements. The statement below leaves for ambiguity as the statement can also be true. 
$$
\begin{gather*}
x > 0 \\ \\
\end{gather*}
$$
$$
q \equiv \bot
$$

### Unsatisfiable 
A statement that is always false regardless.  For example, the statements form the Law of Excluded middle is an unsatisfiable statement. If $\phi \lor ¬\phi$ then $\phi \land ¬\phi$ is unsatisfiable. 

## Differences between
Valid means that statement is always true regardless. However invalid means that a statement is not always true. 

For example, if we have an assertion for the statement to be true and a counterexample $\rho$ is found, then the statement is invalid for that $\rho$.

For example, if 

# Double negation rule
This means that a double negated statment will produce an unchanged statement from the original proposition. 

# De Morgan's Law
De Morgan's law states that it is possible to flip back and forth between disjunction and conjunction using the negation operator. 
$$
\begin{gather*}
¬( \phi \wedge \psi) \equiv ¬ \phi \wedge ¬\psi \\ \\
¬(\phi \lor \psi) \equiv ¬\phi \lor ¬ \psi
\end{gather*}
$$
## Implication 
$$
\begin{gather*}
p \implies ( q \implies r) \\ \\
q \implies p \equiv ¬q \wedge p \\ \\
p \wedge q \implies r \\ 
\end{gather*}
$$


A counter example to the implication law 
	- $p$ is true
	- Counterexample to $q \implies r$
		- $q$ is true
		- $r$ is false
A counter example to the implication law