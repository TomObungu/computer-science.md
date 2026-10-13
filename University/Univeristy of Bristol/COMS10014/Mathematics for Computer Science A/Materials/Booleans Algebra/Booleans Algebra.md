# Propositions 
A proposition is a statement that can be true or false. That is a Boolean valued statement.  

Propositions must be evaluated correctly according to the context. For example, "it is raining" depends on the current weather and "$x<y$" depends on the value of $x$ and $y$.

## Propositional Formulas
A propositional formula also refereed to simply a formula or proposition, is a term built from Boolean operators, e.g. conjunction and disjunctions as well as propositional variables e.g. $p$, $q$, $r$, $x$ and constant Boolean values $\top$ and $\bot$.  

The greek letters $\phi$ and $\psi$ are typically used to represent arbitrary propositional formulas. For example $p \land r \implies r$ is a proposition formula and $p$, $q$ and $r$ are its propositional variables. Propositional variables can constitute propositions as well. Thus $p$ is both a propositional variable and a proposition.

## Syntax vs. Semantics
Propositional formulas should be thought of as trees spoken of last time. They are syntactic objects which refers to how they are written. Whereas semantics refer to what something means. For example $x+y$ and $y+x$ are syntactically distinct but have the same semantics.

## Truth Tables and Assignments
Truth tables are semantics of propositional formulas. Each row in a truth table describes a particular context in which a formula may be evaluated. For instance $p \land q\implies r$ evaluates to true in the row where $p=\bot$ and where $q = \bot$.

# Equivalences
Two propositions $\phi$ and $\psi$ are said to be equivalent if they have the same truth table. In which case, we write $\phi\equiv \psi$. There are several equivalences that come up when working with Propositions and Boolean operators. These equivalences are known as Boolean Algebra. 

## Associativity and Commutativity
The associativity and commutativity of a conjunction and disjunction. For any propositional formulas $\phi$, $\psi$ and $\rho$ have the equivalences 