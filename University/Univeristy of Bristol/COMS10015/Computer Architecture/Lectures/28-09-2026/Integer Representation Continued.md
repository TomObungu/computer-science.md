Consider a variable $\hat{x}$ that maps to a value $x$ and $\hat{y}$ that maps to $y$:
$$
\begin{gather*}
\hat{x} \mapsto x \\ \\
\hat{y} \mapsto y
\end{gather*}
$$

In this case the values $\hat{x}$ and $\hat{y}$ are bit representations that map to integer values $x$ and $y$. Now consider another bit representation $\hat{r}$ that can map to an integer sum between $x$ and $y$. 
$$
\begin{gather*}
\hat{r} = x + y
\end{gather*}
$$
It is possible to represent $\hat{r}$ as a function of $x$ and $y$. 
$$
f =(\hat{x},\hat{y}) = \hat{r} \mapsto x + y
$$
In this case, $f$ is a function that has an action on $\hat{x}$ and $\hat{y}$ such that it performs an addition action of $+$ on $x$ and $y$. The sequence of the function of $f$ can be as followed:
1. Accepts a $n$-bit
	1. **addend** $\hat{x}$ and $\hat{y}$ as input 
	2. Produces $(n+1)$ bit sum as $\hat{r}$ as a result. 

# Agenda : produce a design for $f$
Now consider the case of producing designs for function $f$ which function correctly and satisify pertinent quality metrics. That is is efficient in time and space $(O(n), \Omega ()))$

## Addition in theory
Consider the familiar decimal addition found in base $10$:
$$
\begin{gather*}
x = 107_{(10)} \mapsto 1 \ 0 \ 7 \\ 
y = 14_{(14)} \ \ \mapsto 0 \ 1 \ 4 \\
\hline 
c = \qquad \qquad  0 \ 1 \ 0 \ \\
r = \qquad \qquad   1\ 2 \ 1
\end{gather*}
$$

# Algorithm in place

Below is the formal mathematical representation of the above algorithms on addition. Is is rigorous in the case that it contains the base $b$ and carry digit $c$ as  variables. This adds versatility and makes it a general purpose algorithm that be universally shared. 

1. r $\gets 0, c_{0} \gets c_{i}$
2. $\mathbf{for} \ i = 0 \ \mathbf{upto} \ n-1 \mathbf{step} +1  \ \mathbf{do}$
	1. $r_{I} \gets (x_{i} + y_{i} + c_{i})$
	2. if $(x_{i} + y_{i} + c_{i}) < b \ \mathbf{then} \ c_{i} \gets 0 \ \mathbf{else}\ c_{i} \gets 1$
3. $\mathbf{end}$
4. $c_{0} \gets c_{n}$
5. $\mathbf{return} \ r, c_{0}$

This algorithm below forms the basis of an adder function. 

* circuit goes here*


This lines below within the algorithm  is analagous to a function that takes in 3 inputs that maps to a output of two variables:
	1. $r_{I} \gets (x_{i} + y_{i} + c_{i})$
	2. if $(x_{i} + y_{i} + c_{i}) < b \ \mathbf{then} \ c_{i} \gets 0 \ \mathbf{else}\ c_{i} \gets 1$
$$
f_{i}: \{0,1\}^{3} \to \{0, 1\}^{2}
$$

| $c_{in}$ | $x$ | $y$ | $r$ | $c$ |
| -------- | --- | --- | --- | --- |
| 0        | 0   | 0   | 0   | 0   |
| 0        | 1   | 0   |     |     |
| 0        | 1   | 1   |     |     |
| 0        | 0   | 1   |     |     |
By taking in the $c_{o}$ from the previous adder in unison with the other variable inputs for each adder, the combination of them termed a ripple-carry adder. The connection or carry bit $c_{0}$ is what connects between adders

# Cases of signed and unsigned integers
When dealing with unsigned integers for $\hat{x}$ and $\hat{y}$, the magnitude of $r=x+y$ can exceed what is represented via $\hat{r}$. 

1. If $\hat{x}$ and $\hat{y}$ are unsigned, and 
2. If $\hat{x}$ and $\hat{y}$ are signed and signs between them are incorrect, then there is a overflow error

Adding two positive 