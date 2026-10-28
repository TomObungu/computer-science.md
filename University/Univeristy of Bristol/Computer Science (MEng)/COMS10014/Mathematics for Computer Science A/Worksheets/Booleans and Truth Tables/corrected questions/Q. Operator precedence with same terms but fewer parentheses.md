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
1. In the first case the brackets can be removed around $(r)$.
$$
\begin{gather*}
(p \implies q)\implies (r) \to (p\implies q)\implies r
\end{gather*}
$$
Remember that if there are no parenthesis, by convention. Take this assumption mentally even if there are no brackets visually. 
$$
p \implies q \implies r \to p \implies (q \implies r)
$$
2. The second case can be explained with associativity
$$
(p \lor q) \lor ( q \land r) \to p \lor q \lor q \land r
$$
3. The third case can is left unchanged. This is due to that if changing the terms to be expressed in De Morgan's law, then it would involve changing the terms. 
$$
¬(p \land q) \to ¬(p \land q)
$$
4. For the fourth case, the terms are also left unchanged due if the terms were expressed in distributivity, then there would be a change of terms again
$$
(p \lor q) \land r \to (p \lor q) \land r
$$
5. For the fifth case it would involve removing all the parenthesis to let conventional precedence take over
$$
p \land q \implies p \implies q
$$