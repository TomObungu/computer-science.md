![[Pasted image 20261015185827.png]]
![[Pasted image 20261015185850.png]]
With questions like this, it is tempting to change expressions like 
$$
(p \implies q) \implies (r)
$$
To their Boolean terms:
$$
\begin{gather*}
¬(¬p \lor q ) \lor r \\ \\
(p \land ¬q) \lor r \\ \\
p \lor r \land p \lor ¬q
\end{gather*}
$$

to remove the parenthesis entirely. However this does not ensure the terms are kept the same. 

Below are the following equivalences with the same terms:
1. The first case 
2. The second case can be explained with associativity
$$
(p \lor q) \lor ( q \land r) \equiv p \lor q \lor q \land r
$$
