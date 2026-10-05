# Limitations of Propositional Logic
In propositional logic, there are atomic propositions meaning they are only binary statements that are either true or false. They are connected using $\lor$, $\land$, $¬$ , $\implies$. 

Think about statements below involving variables
- All students should attend the class in logic
- There is a student who did not attend the class in logic
- The Student $x$ got full marks in the exam. 

With propositional logic, there is no formal way to represent logic with variables. 

## Predicate logic
Predicates are statements that contain variables. Consdier the statement
"The temperature is greater than 18 degrees". The temperature is the subject and "greater than 18" is the property being asserted about the subject. This is the predicate. 

It is possible to define the $P$ to mean the predicate and deinfe $P(t)$ to represent a propositional function .  Predicates can have any number of variables e.g. let $P(x,y)$ denote $x = y + 5$. The values of $P(10,5)$ can be evaluated as propositional statements. 

# Quantification 
Quantification allows the expression of the extent to which a predicate is true to some range of values. Furthermore language quantifiers include:
- Some
- All 

# Qunatifiers
## Universal quantifier
The universal quantifier $\forall$ means "for" all elements in the domain
## Existential quantifier
The existential quantifer $\exists$, "there exists" one or more elements in the domain. 

For example consider the statement the "Consider $P(x)$ be $x^{2}>x$, $\forall xP(x)$ to be true for $\mathbb{Z}$ but not $\mathbb{R}$"

$\forall xP(x)$ is false when there is an $x$ in the domain for which $P(x)$ is false. 

The statement $\exists xP(x)$ is true when there is an $x$ within the domain for which $P(x)$ is true. Such $x$ is called a witness. 

However the statement $\exists xP(x)$ is only false when every $x$ is false in the domain of $P(x)$.

However the statement $\forall xP(x) \implies \exists xP(x)$ has the underlying assumption of the set not being empty. 

For finite domains, all elements can be listed i.e $$D = \{x_{1}, x_{2}, x_{3}\dots\}$$
The universal quantifier is equivalent to the conjunction of all elements. 
$$
\forall xP(x) = P(x_{1}) \land  P(x_{2}) \land \dots  P(x_{n})
$$

The existential quantifier is equivalent to the disjunction of all elements. 
$$
\exists xP(x) = P(x_{1}) \lor  P(x_{2}) \lor \dots  P(x_{n})
$$
# Specific Domains
For specific domains, $D$ it is possible to write
$$
\begin{gather*}
\forall x:D.P(x)
\end{gather*}
$$
More explcitly this is defined as:
$$
\forall x.(x \in D \implies P(x))
$$
In some textbooks there

# Empty domains
The statement $\forall xP(x)$ is vacuously true for an empty set. The empty set can be defined as:
$$
D = \phi
$$

# Precedence
Quantifiers have higher precedence than all connectives from propositional logic. For example the statment:
$$
\forall xP(x) \lor Q(x) = (\forall P(x))\lor (Q(x))
$$
# Bound and free variables 
A variable $x$ is bound when a quantifier is used on $x$. In $\forall xP(x)$ the variable is bound by the univeral quantifier. 

A varaible that not bound is said to be free. In $\forall xP(x,y)$ the variable $y$ is a free variable. 

## Important
**All the the variables in functions in a propositional statement must either be bound or have a value assigned to them.**

# Scope
Quantifiers bind variables with a scope. In $\forall x(\exists x(P(x)\implies(Q(x)))$, the scope universal quantifer scope is for all varaibles. 

# De Morgan's Law For Quantifiers
$$
\begin{gather*}
¬\forall xP(x) \equiv ¬\exists xP(x) \\ \\
¬\exists xQ(x) \equiv \forall x¬Q(x)
\end{gather*}
$$
Consider the statment, every student has taken the class test in logic. The negation of this statement is "It is not the case that every student has taken the class test in logic". 

# Nesting quantifiers 
$$
\forall y \exists xMother(x,y)
$$
By 



