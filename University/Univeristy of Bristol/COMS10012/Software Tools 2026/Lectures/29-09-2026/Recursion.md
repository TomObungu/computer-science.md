# Triangle Numbers
$$
t:N \to N
t(n) = \begin{cases}
\begin{gather*}
t = 1 \qquad \text{If } n = 1 \\ \\ \\
n + t(n-1) \qquad \text{otherwise}
\end{gather*}
\end{cases}
$$
# Proof
$$
\begin{gather*}
\text{Claim:} \\ \\
t(n) = \frac{n(n+1)}{2} \\ \\
\text{Consider the case: } n = 1 \\ \\
LHS = 1 
\end{gather*}
$$



$$
\phi  = \frac{1 + \sqrt{ 5 }}{2}
$$


# Padovan sequence
$$
\begin{gather*}
T_{1} = 1,\ T_{2} = 1, \ T_{3} =1, \ T_{4} = 2, \ T_{5} = 2 \dots. \\ \\
\\ \\
T_{1} = 1 \\ \\
T_{2} = 1 \\ \\
T_{3} = T_{2} + T_{3}, \\ \\
T_{4} = T_{3} + T_{2}, \\ \\
T_{5} = T_{4} + T_{5}, \\ \\

\text{In general:} \\
T_{n} = T_{n-2} + T_{n-3}


\end{gather*}

$$

# Lucas number
$$
\begin{gather*}
T_{1} = 2 \\ \\
T_{2} = 1 \\ \\
T_{3} = T_{1} + T_{2} \\ \\
T_{4} = T_{2} + T_{3} \\ \\
T_{5} = T_{3} + T_{4} \\ \\ 
\text{In general:} \\
T_{n} = T_{n-2} + T_{n-1}
\end{gather*}
$$