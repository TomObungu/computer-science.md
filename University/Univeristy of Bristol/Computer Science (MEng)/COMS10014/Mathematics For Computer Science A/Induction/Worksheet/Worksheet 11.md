5. For each of the following claims, write a proof by induction:
(1) $\sum_{i=0}^{n}2^{i} = 2^{n+1}-1$
$$
\begin{gather*}
\text{Consider the case of n = 1} \\ \\
L(n) = \sum_{i=0}^{n}2^{i} \qquad R(n) = 2^{n+1}-1 \\
L(0) = 2^{0} = 1 \qquad R(0) = 2^{1}-1 =1  \\ \\
L(0) =R(0) \\ \\
\text{Thus the case holds for n = 0} \\ \\
\text{Assuming L(k)=R(k) holds} \\ \\
\sum_{i=0}^{k}2^{i} = 2^{k+1}-1 \\ \\
\text{Consider the case of n=k+1} \\ \\
\sum_{i=0}^{k+1}2^{i} = \sum_{i=0}^{k}2^{i}  + (2^{k+1}) \\ 
= \frac{2^{k+1} - 1}{2-1} + 2^{k+1 } \\ \\
= 2(2^{k+1})- 1  = 2^{k+2} -1 = 2^{(k+1)+2}-1 \\ \\
\text{Thus the case for n=k+1 holds} \\ \\
\text{Thus } \forall i \in \mathbb{N}  \sum_{i=0}^{n}2^{i} = 2^{n+1}-1
\end{gather*}
$$
(2) $\sum_{i=0}^{n}r^{i} = \frac{1-r^{n+1}}{1-r}$, for $r\neq_{0}$ and $r\neq_{1}$
$$
\begin{gather*}
\text{Consider the case of n = 1} \\ \\
L(n) = \sum_{i=0}^{n}r^{i} \qquad R(n) = \frac{1-r^{n+1}}{1-r}\\
L(0) = r^{0} = 1 \qquad R(0) = \frac{1-r^{n+1}}{1-r} =\frac{1-r}{1-r}=1  \\ \\
L(0) = R(0) \\ \\
\text{Thus the case holds for n = 0} \\ \\
\text{Assuming L(k)=R(k) holds} \\ \\
\sum_{i=0}^{k}r^{i} = \frac{1-r^{k+1}}{1-r} \\ \\
\text{Consider the case of n=k+1} \\ \\
\sum_{i=0}^{k+1}r^{k} = \sum_{i=0}^{k}r^{i} +r^{k+1} = \frac{1-r^{k+1}}{1-r} + r^{k+1} \\ \\
= \frac{1-r^{k+1}+r^{k+1}- r^{k+2}}{1-r} = \frac{1-r^{k+2}}{1-r}\\ \\
\text{Thus the case for n=k+1 holds} \\ \\
\text{Thus } \forall i \in \mathbb{N} \sum_{i=0}^{n}r^{i} = \frac{1-r^{n+1}}{1-r}, r\neq_{0} \text{and } r\neq_{1}
\end{gather*}
$$
