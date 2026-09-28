Consider a variable $\hat{x}$ that maps to a value $x$ and $\hat{y}$ that maps to $y$:
$$
\begin{gather*}
\hat{x} \mapsto x \\ \\
\hat{y} \mapsto y
\end{gather*}
$$

In this case the values $\hat{x}$ and $\hat{y}$ are bit representations that map to integer values $x$ and $y$. Now consider another bit representation $\hat{r}$ that can map to an integer sum between $x$ and $y$. 
$$
\begin{gather*}
\hat{r} = x + y
\end{gather*}
$$
It is possible to represent $\hat{r}$ as a function of $x$ and $y$. 
$$
f =(\hat{x},\hat{y}) = \hat{r} \mapsto x + y
$$
In this case, $f$ is a function that has an action on $\hat{x}$ and $\hat{y}$ such that it performs an addition action of $+$ on $x$ and $y$. The sequence of the function of $f$ can be as followed:
1. Accepts a $n$-bit
	1. **addend** $\hat{x}$ and $\hat{y}$ as input 
	2. Produces $(n+1)$ bit sum as $\hat{r}$ as a result. 

# Agenda : produce a design for $f$
Now consider the case of producing designs for function $f$ which function correctly and satisify pertinent quality metrics. That is is efficient in time and space $(O(n), \Omega ()))$




