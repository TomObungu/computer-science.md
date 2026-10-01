# Disjunction
# 1. 
Claim. $(p\implies q) \implies (q \lor p \implies q)$
Proof.
$$
\begin{gather*}
1. \text{Assume } p\implies q \\
2. \text{Assume } p \lor q \\
3. \text{Assume } q \\
4. q \text{ by assumption} \\
5. \text{Assume } p \\
6. q \text{ by elimination on 1,4 }\\
7. p \implies q  \text{ by elimination on 4,6 } \\
8. q \lor p \implies q \text{ by } \implies \text{introduction on 2,7} \\
9. (p\implies q) \implies (q \lor p \implies q) \text{ by } \implies \text{introduction on 1,8}
\end{gather*}
$$
# 2.
 Claim. $p\implies(p \lor q) \land q$
 Proof. 
 $$
\begin{gather*}
1. \text{Assume p} \\
2. p \lor q \text{ by } \text{ by } \land \text{ introduction on 2, 3} \\ 
3. \text{Assume q} \\
4. (p \lor q) \land q \text{ by } \text{introduction }
\end{gather*}
$$