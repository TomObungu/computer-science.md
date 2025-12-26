In this problem we want to count the number of ways two knights can be placed in a $k \times k$ board without attacking each other

Below is a valid arrangement as the knights are not attacking each other when $k=4$
![[Pasted image 20251226202914.png]]

Below is not a valid arrangement as the knights are attacking each other.
![[Pasted image 20251226202959.png]]

To solve this problem we take this approach:
![[Pasted image 20251226203022.png]]

The number of ways you can place two knights on a chess board is given by:
$$
X = \frac{(n^{2}-1)(n^{2})}{2}
$$
Alternatively, this is just the the nCr formula of:
$$
16C 2 = \begin{pmatrix}
16  \\
2
\end{pmatrix}
$$
Which $nCr$ is:
$$
\frac{n!}{r!(n-r)!}
$$

(Crazy thing is I actually figured both of these out before looking at the solution. I initially figured the nCr approach first)

![[Pasted image 20251226203304.png]]

How ever it is better to use above formula due to implementation of factorial function.