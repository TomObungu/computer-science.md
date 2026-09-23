# What is Algebra?
Algebra is about equality. When you consider the equation, the left hand must equal to the right hand side. As well as that there are two things founded within alegbra, that is, syntax and semantics. The syntax of an algebraic equation is the symbolic representation whereas the semantics of  of an algebraic representation is the meaning.
$$
x + y = z
$$
For example take the equation below. It is true that the left hand side is equal to right hand side. 
$$
x + 0 = x
$$
If we were to take an equation within Boolean Alegebra, it is possible to show equality in the same manner:
$$
(p \wedge q )\lor r \equiv p \wedge q \lor r
$$
# Variables
Greek letters such as $\psi,\phi,\rho$ are variables that stand in for arbitrary proposition. 

# Associativity 
The associativity rule means that algebraic statments are true regardless of the placement of parenthesis. The equation belove evaluate to true. If the individual truth tables were to be drawn out, comparing the truth tables will show the equivalence. This is the case for the conjunction.
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
# Idempotence
The defintion of idempotence means that the algebraic expression is left unaffected if the terms are repeated. For example consider the expression below. 
$$
\begin{gather*}
\phi \wedge \phi \equiv \phi \\ \\
\phi \lor \phi \equiv \phi
\end{gather*}
$$
## The law of the excluded middle
This law means that a variable in disjunction with itself will always evaluate to true. 

This is because the that using the disjunciton (OR) table with $\phi$ wil always evaluate to true due to $\phi$ being true within itself. 
$$
\begin{gather*}
\phi \lor ¬\phi \equiv \top \\ \\
\phi \wedge ¬\phi \equiv \bot
\end{gather*} 
$$

# Tautology
A tautology is a proposition that is universally true regardless of the statement.

### Valid 
A statemennt that is always true. For example the equation below is a valid claim:
$$
x > 0 \implies x > -100
$$
### Invalid
A statement that is not always true. 
$$
\phi \neq \top 
$$
### Satisfiable 
A statement that **can** be true. A statement that is not always false. Below are satisfiable statements:
$$
\begin{gather*}
x > 0 \\ \\
q \equiv \bot
\end{gather*}

$$
### Unsatisfiable 
A statement that is always false regardless. 


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


