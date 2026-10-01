# Disjunction
Claim. $(p\implies q) \implies (q \lor p \implies q)$
Proof.
$$
\begin{gather*}
1. \text{Assume } p\implies q \\
2. \text{Assume } p \lor q \\
3. \text{Assume } q \\
4. q \text{ by assumption} \\
5. \text{Assume } p \\
6. p \text{ by assumption }\\
7. p \implies q  \text{ by elimination on 3,5} \\
8. q \lor p \implies q \text{ by } \implies \text{introduction on 2,7} \\
9. (p\implies q) \implies (q \lor p \implies q) \text{ by } \implies \text{introduction on 1,8}
\end{gather*}
$$