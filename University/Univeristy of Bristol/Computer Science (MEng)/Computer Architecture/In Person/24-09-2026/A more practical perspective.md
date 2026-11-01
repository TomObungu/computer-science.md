Descional operators such as $\&\&$ are operators that are computing a descision.

Computational operators such as $\&$ are computational operators that are computing an operation such as bitwise operators. 
 
# Question
Simplify the Boolean expression
$$
\begin{gather*}
f = ¬(a \lor b) \wedge ¬(c \lor d \lor e) \lor ¬(a \lor b) \\ \\
\text{Commutativity} \\ \\
= ¬(a \lor b) \lor (¬(a \lor b) \wedge ¬(c \lor d \lor e)) \\ \\
\text{Absorption} \\ \\
= ¬(a \lor b)
\end{gather*}
$$

# Sum of Product Form
When the expression is written as a sum OR and compromise of a product of AND variables. That is within the bracket terms, each term is a product of AND. It is said to be in Sum of Products (SoP) form. The terms within the brackets are called miniterms 

$$
\begin{gather*}
\underbrace{ \underbrace{ (a \wedge b \wedge c) }_{ \text{minterms} } \lor (d \lor e \lor f) }_{ \mathbf{\text{Sum of Products (SoP form)}} }
\end{gather*}
$$
Another example of valid Sum of Products form is 
$$
(¬a \wedge b \wedge c) \lor (d \wedge ¬e\wedge f) 
$$

# Product of Sums Form
When the expression within the brackets is a product of disjunctions (OR) and the product of the bracket terms is a conjunctive operator (AND), it is said to be in Product of Sum form (PoS). The terms within the brackets are called maxterms.
$$
\underbrace{ \underbrace{ (a \lor b \lor c) }_{ \mathbf{\text{maxterms}} } \wedge(d \lor e \lor f) }_{ \text{Product of Sums Form} }
$$
# Don't care entries
Truth tables can accomodate values that don't change the outcome of the binary state regardless of the the value. For example take the table below:

| $x$ | $y$ | $r$ |
| --- | --- | --- |
| $?$ | 0   | 1   |
| 0   | 1   | $?$ |
| 1   | 1   | 0   |

This is the case that on the LHS for an input, $?$ is a wildcare input it means 0 and $1$. That is the the value is the same regardless of the state. A compression of two truth rows into one.


For the RHS it means $0$ or $1$. We can select which one to option to 

# Electronic Design Automation (EDA)
EDA tools can be used in manipulation, translation, simulation and vertication when dealing with Boolean Algebra,

# NAND and NOR

The NAND and NOR operators are universally complete. This means that every Boolean function can be expressed using the single NAND or NOR operator. 

