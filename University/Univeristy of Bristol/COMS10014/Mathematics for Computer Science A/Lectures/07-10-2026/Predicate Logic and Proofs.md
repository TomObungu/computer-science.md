# Syntax of Predicate Logic
Formulas in predicate logic can be built from variables, constants, connectives and functions.
- Variables are placeholder values e.g. $x$, $y$, $z$
- Constants are set of constants e.g. $MAX$, $24$, $Anna$
- Connectives are all of the connectives from propositional logic e.g. $\lor$, $\land$, $\implies$
- Function is a set of n-ary functions  

There are also predicates and quantifiers
- Predicates are a set of functions that return truth values
- Quantifiers such as $\exists, \forall$

An atomic formula consists of a function  $P \in PL$ and $P(t_{1},t_{2}, t_{3})$, where $t_{n}$ are valid terms. 

# Informal Proofs 
Proof Strategies
- Direct proofs means the goal is $P\implies$Q. The approach is assuming $P$ and deriving $Q$
- Indirect proof (contrapositive) means the goal is $P\implies Q$. The approach is $¬Q$ and deriving $¬P$
- Contradiction means the goal is to prove $P$. The approach is assuming $P$ and deriving $\bot$
- Case distinction means the goal is to prove $P$. The approach splitting the proof into  exhaustive cases

# Connecting Informal Proofs to Natural Deduction 
