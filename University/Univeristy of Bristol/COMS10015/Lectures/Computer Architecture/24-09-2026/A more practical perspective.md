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
When the expression is written as a sum OR and compromise of a product of AND variables. That is within the OR terms, each term is a product of AND. It is said to be in Sum of Products form. The terms within the brackets are called miniterms 

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


# Don't care entries
Truth tables can accomodate values that don't change the outcome of the binary state regardless of the the value. For example take the table below:

| $x$ | $y$ | $r$ |
| --- | --- | --- |
| $?$ | 0   | 1   |
| 0   | 1   | $?$ |
| 1   | 1   | 0   |

This is the case that on the LHS for an input, $?$ is a wildcare input it means 0 and $1$. That is the the value is the same regardless of the state. A compression of two truth rows into one.


For the RHS it means $0$ or $1$. We can select which one to option to 

# Electronic Design Automation

# NAND and NOR

The NAND and NOR operators are universally complete. This means that every Boolean function can be expressed using the single NAND or NOR operator. 

Below are the universal Boolean operators written in NAND-form:
$$
¬x \equiv x 
$$