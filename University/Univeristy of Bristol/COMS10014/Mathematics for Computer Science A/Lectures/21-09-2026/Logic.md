# Propositions
A proposition is either a statement that is either true of false. True and false are the two Boolean values. The represent the truth value of a proposition - the answer to a propositional question.

For example $12 < 14$ is a proposition and it's associated boolean value is $\top$. 

# Notation for Booleans
The propositional symbols for Boolean in mathematical set logic can be represented as :
$$
\begin{gather*}
\top - \text{True} \\ \\
\bot - \text{False}
\end{gather*}
$$
We can capture the output of a Boolean function for every possible combination using truth tables. Inputs sit left of the divider and the outputs to the right.

Boolean logic can also be seen in circuits and bits as $1 / 0$, in everyday logic and programming languages as true and false.

# Truth tables
A truth table is a table capturing the output of a Boolean function for every possible input combination. Inputs sit left of the divider, outputs to the right and every combination of inputs must appear. If this is the case, the table is incomplete.

Consider a truth table with everyday propositional statements:

| Night Mode Option? | Is it past 5pm? | Night Mode? |
| ------------------ | --------------- | ----------- |
| $\bot$             | $\bot$          | $\bot$      |
| $\bot$             | $\top$          | $\bot$      |
| $\top$             | $\bot$          | $\bot$      |
| $\top$             | $\top$          | $\top$      |

The example above can be used for let's say when a website switches to night mode just if the nightmode option is selected AND it's past 5pm. 
# Conjunctions (AND)
The symbol for a conjunction in formal logic is $\wedge$.
The conjunction of two propositions. The result is true if both sub-propositions are true. This is true if the "conjuncts", are true. Below is an example table showing the conjuctive propositions between $p$ and $q$:

| p      | q      | $p \wedge q$ |
| ------ | ------ | ------------ |
| $\bot$ | $\bot$ | $\bot$       |
| $\bot$ | $\top$ | $\bot$       |
| $\top$ | $\bot$ | $\bot$       |
| $\top$ | $\top$ | $\top$       |

# Disjunctions (OR)
The  symbol for a disjunction in formal logic is $\lor$. The disjunction of two proposiitions. The result is true if either on of sub-propoistions are true. 

| p      | q      | $p \lor q$ |
| ------ | ------ | ---------- |
| $\bot$ | $\bot$ | $\bot$     |
| $\bot$ | $\top$ | $\top$     |
| $\top$ | $\bot$ | $\top$     |
| $\top$ | $\top$ | $\top$     |
# Negation (NOT)
The symbol fo a negational propositoin in formal logic is $¬$
A unary operator, i.e with only one input, that flips true to false and false to true. Unlike every English "or", it's also true when both inputs are true. 

# Implication 
Encodes "if p then q." We refer to p as the antecedent (left of the arrow), and q is the consequent (right).

True if either the antecedent is false, or the consequent is true. The truth table as this, where $p$ is the antecedent and $q$ is the consequent. 

| p      | q      | $p \implies q$ |
| ------ | ------ | -------------- |
| $\bot$ | $\bot$ | $\top$         |
| $\bot$ | $\top$ | $\top$         |
| $\top$ | $\bot$ | $\bot$         |
| $\top$ | $\top$ | $\top$         |

This can also be represented in regular Boolean expressive form:
$$
¬p \wedge q
$$
As well as that, consider the logic of $p\implies q$ using a logical statement:
E.g. (If it is past 5pm, then it implies that work has finished)

If work had finished and it was not 5pm then the there wouldn't evidence to support the implication. Likewise if it was 

## Implication and vacuous truth
For example take a statement such as "If pigs can fly then, then work has finished". In this scenario since the statement is always a claim that doesn't hold any value, then on the truth table, the statement will always return true. Regardless of any input the result will always be $\top$

# Alternative Notation

# Operator Precedence
The hierachy of operator precedence is:
1. Parenthesis
2. Negation
3. Conjunction
4. Disjunctions 

# Associativity
A binary operator $o$ is associative if $( p )$

Implication is not associative. By convention

For example 
$$
\begin{gather*}
p \implies q \implies r \equiv p \implies (q \implies r) \\ \\
p \implies q \implies r \neq (p \implies q) \implies r \\ 
p \implies q \implies r \neq p \implies (q \implies r)
\end{gather*}
$$

# Functional Completeness
A collection of Boolean functions is functionally complete if it can express any arbitrary Boolean function. For each row where the function is true, build the term that matches the row using conjunction, negation and disjunction. 

## Theorem 1
$\wedge, \lor$ and $¬$ are together functionally complete. 

For example this exclusive OR function (XOR) $\oplus$can entirely be represented entirely out 

$$
p \oplus q \equiv f(p,q) = (p \wedge ¬p) \lor (¬p \wedge q)
$$










