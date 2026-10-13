Two propositions $\phi$ and $\psi$ are said to be equivalent if they have the same truth table. In which case, we write $\phi\equiv \psi$. There are several equivalences that come up when working with Propositions and Boolean operators. These equivalences are known as Boolean Algebra. 

## Associativity and Commutativity
The associativity and commutativity of a conjunction and disjunction. For any propositional formulas $\phi$, $\psi$ and $\rho$ have the equivalences


$$
\begin{array}{c|c|c} \\
\text{ }  & \text{Associativity}  & \text{Commutativity} \\ \\
\hline \\ 
 \text{Conjunction}  & \phi \land (\psi \land p) \equiv (\phi \land \psi) \land p  & \phi \land \psi \equiv \psi \land \phi \\ \\
\hline 
\text{Disjunction }  &  \phi \lor (\psi \lor p) \equiv (\phi \lor \psi) \land p & \phi \lor \psi \equiv \psi \lor \phi
\end{array}
$$
It is possible to verify this equivalence by comparing their truth tables. 

Commutativity means that these operations are insensitive to the order of their arguments. In other words, $p \land q$ is equivalent to $q \land p$. 

# Distributivity
The distributivity of conjunction and disjunction, for any propositional formulas $\phi$, $\psi$ and $\rho$ have the equivalences:
$$
\begin{gather*}
\phi \land (\psi \lor \rho) \equiv (\phi \land \psi) \lor (\phi \land \psi) \\ \\ 
\phi \lor (\psi \lor \rho) \equiv (\phi \lor \psi) \land (\phi \lor \psi) \\ \\
\end{gather*}
$$