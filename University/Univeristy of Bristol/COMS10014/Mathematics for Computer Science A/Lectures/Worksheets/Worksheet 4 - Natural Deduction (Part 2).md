# Disjunction
1. Claim. $(p\implies q) \implies (q \lor p \implies q)$
Proof.
$$
\begin{gather*}
2. \text{Assume } p\implies q \\
3. \text{Assume } p \lor q \\
4. \text{Assume } q \\
5. q \text{ by assumption} \\
6. \text{Assume } p \\
7. q \text{ by elimination on 1,4 }\\
8. p \implies q  \text{ by elimination on 4,6 } \\
9. q \lor p \implies q \text{ by } \implies \text{introduction on 2,7} \\
10. (p\implies q) \implies (q \lor p \implies q) \text{ by } \implies \text{introduction on 1,8}
\end{gather*}
$$
11. 