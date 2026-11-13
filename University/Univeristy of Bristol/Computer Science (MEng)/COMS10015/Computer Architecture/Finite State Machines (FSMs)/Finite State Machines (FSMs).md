A FSM is an idealised computer which at a given point in time, it is in one of a set of finite set of states. 

A string $X$ with respect to some alphabet $\sum$ is a sequence of finite length, whose elements are members of $\sum$. 
$$
X = \langle X_{0}, X_{1},\dots X_{n-1} \rangle
$$
A language $\Lambda$ is a set of strings $X$.

C accepts an input string with respect to some $\sum$, one symbol at a time. C either rejects the input string or accepts the input string. 

If $C$ every string in some $\Lambda$. $\Lambda$ is the language of $C$.

# Definition
A (deterministic) Finite State Machine is a tuple
$$
C = (S,s,A,\Sigma,\Gamma, \delta,\omega)
$$
Where $S$ is a finite set of states that include a start state $s\in S$, $A$ is a finite set of accepting states such that $A \subseteq S$, $\delta$ is a transition function such that $\delta:S \times \sum \to S$ and an output function $\omega:S \to \Gamma$ (known as a Moore FSM). 

A Mealy FSM has the case of an empty input $\epsilon$, which means a transition can always occur.

# In Theory

Double circles around the diagram means that the symbol is in an accepting state, That is $A= \{S_{Odd}\}$

You could implement a FSM like this
$$
\text{arithmetic experssion} 
$$