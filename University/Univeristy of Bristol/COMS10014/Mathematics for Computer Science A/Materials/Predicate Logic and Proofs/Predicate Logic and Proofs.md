# Predicate Logic as a Formal Language
Predicate logic allows objects in a domain and their properties and relations. The idea is a two-layer structure. A lower layer of terms and an upper layer of formulas (statements about the objects).

## Lower layer - Terms
The lower layer consists of constants, variables and functions. 

A constant can include a named object such as integers, or "Gromit" or "Wallace".

A variable is a placeholding value ranging over a domain e.g. $x$, $y$, $z$. 

Functions which may take in multiples variables as input to produce an output. Each function has a fixed arity (number of inputs).  For example, the function $f(x)$ is a unary function, $day(dd,mm,yyyy)$ is a tenary function. A function applied to terms produces a new term. 

# Upper layer - Tormulas
The upper layer consists of predicates, propositional connectives and quantifiers. 

A predicate takes in one terms and inputs and outputs  boolean values. For example $=$ is  a built in binary predicate. For example $isEven(x)$ is a predicate.

A propositional connectives such as $\top$, $\bot$, $\lor$, $\land$, $\oplus$, $\implies$ and $ $

A all quantifiers such as $\forall$ and $\exists$

# Example 1
Consider a predicate logic over people. Let the constants be $\{\text{Anna}, \text{John\}}$, the predicates $\{\text{Younger}, \text{Mother}\}$