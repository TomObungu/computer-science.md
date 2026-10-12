Sequential logic allows modelling of inputs and outputs to be discrete rather than continuous. This mimics the behaviour of how the programs we write are handled e.g Running a Python program runs step by step, line-by-line

# SR Latches Continued
## Problem #2 - Control of updates
The following SR latch implementation allows control of when the updates occur. This is through the introduction of AND gates and the enable $en$ signal. This through the ANDING of S and R plus an enable signal. This enable signal could be clock or an any arbitrary signal. 
![[Pasted image 20261012130338.png]]
$$
\begin{gather*}
en = 0 \implies S' = S \wedge en = S \land 0 = 0 \\
\implies R' = R \wedge en = R \land 0 = 0  \\ \\
en = 1 \implies S' = S \wedge en = S \land 1 = S \\
\implies R' = R \wedge en = R \land 1 = R
\end{gather*}
$$
## Problem #3 - Metastability
The is the issue of S and R being 0 and 1 simultaneously. This is through forcing $R$ to be $¬S$ so it is possible to get either $S=0$ and $R=1$ or $S=1$ and $R=0$. This now a standard level triggered SR latch. 
![[Pasted image 20261012131055.png]]


# Problem #4 - Edge triggered activiation (D-type)
