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


The only the that remains is calculated the number of ways to place 2 knights so they wont attack each other:

We can think about it by consider the attacking squares that one knight attacks for each square of the chess board

When the knight is on the top left most tile, it attacks to squares. We consider this for each square and add this number to the sum $Y$

![[Pasted image 20251226204129.png]]

We can represent the attacking squares of a knight on each square by writing its number in the tile:

![[Pasted image 20251226204445.png]]
However the approach of going through each cell and counting the number of attacking squares is not a valid solution.

For this problem, we have $1 \leq  n <= 10000$, a computer running C++ can perform about $10^{8}$ operations. Thus if we have the of the board is $n^{2}$ and we must return the number of ways two knights cannot attack each other for every $n_{i}$ up to $n$. This gives a time complexity of:
$$
\frac{(n)(n-1)}{2}(n^{2})
$$
Which is roughly quartic / cubic time complexity.

Thus, it possible 