# Syntax of Predicate Logic
Formulas in predicate logic can be built from variables, constants, connectives and functions.
- Variables are placeholder values e.g. $x$, $y$, $z$
- Constants are set of constants e.g. $MAX$, $24$, $Anna$
- Connectives are all of the connectives from propositional logic e.g. $\lor$, $\land$, $\implies$
- Function is a set of n-ary functions e.g. $f(x), date(dd,mm,yyyy)$

There are also predicates and quantifiers
- Predicates are a set of functions that return truth values $Father()$
- Quantifiers such as $\exists, \forall$

An atomic formula consists of a predicate function  $P(t_{1},t_{2}, t_{3})$, where $t_{n}$ are valid terms. 

# Informal Proofs 
Proof Strategies
- Direct proofs means the goal is $P\implies$Q. The approach is assuming $P$ and deriving $Q$
- Indirect proof (contrapositive) means the goal is $P\implies Q$. The approach is $¬Q$ and deriving $¬P$
- Contradiction means the goal is to prove $P$. The approach is assuming $P$ and deriving $\bot$
- Case distinction means the goal is to prove $P$. The approach splitting the proof into  exhaustive cases
# Proving Universal Statements
# Arbitrary Element strategy
This is to show  $\forall x:D.P(x)$. This is known as the arbitrary element strategy
1. Let x be an arbitrary element of $D$. Make no assumptions of $x$ beyond $x \in D$
2. Show that $P(x)$ holds using any proof strategy 
3. Conclude: "Since x was arbitrary", $\forall x : D.P(x)$ 
# Proving Existential Statments
## Witness startegy
This is to show $\exists x : D.P(x)$. This is known as the witness strategy 
1. Find or construct a specific term $t \in D$
2. Show that $P(t)$ holds
3. Conclude "Therefore $\exists x$ : D.P(x)" taking $x=t$

# Example 
If we have $\forall x.(S(x \implies W(x)))$ and $\forall x.(W(x)\implies Pass(x))$ then $\forall x.(S(x)\implies Pass(x))$
Where $S(x)$ is a student, $W(x)$ and

Proof:
1. Let $x$ be an arbitrary person
2. Assume $S(x)$
3. Since $\forall x.(S(x)\implies W(x))$, in particular $S(x)\implies W(x)$



