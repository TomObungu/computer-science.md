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


## Problem #4 - Edge triggered activation (D-type)
### Solution 1

A first solution to the edge-triggered activation is using a pulse generator to approximate the edges. Below is the design of the pulse generator
![[Pasted image 20261012131657.png]]
Below is the circuit integration of the pulse generator in an SR latch.
![[Pasted image 20261012131718.png]]

### Solution 2
A second solution to edge-triggered activation is splitting a clock cycle into half cycles through two NOT gates.
![[Pasted image 20261012131944.png]]
When $en=0$ the primary latch is enabled. This leads to the input of the left hand latch being $0$ and $1$. Thus the primary latch is enabled. When $en=1$, the secondary latch is enabled. This leads to input of the right hand latch being $1$ and $0$ and thus the secondary latch enables. 

# Abstractions for D-type flip flops 
A D-type latch is described symbolically as a rectangular box. 
![[Pasted image 20261012132357.png]]
Below is the associated behaviour for level-triggered updates. As D alternates, the behaviour 
![[Pasted image 20261012132431.png]]

A D-type edge-triggered flip flop is as below:
![[Pasted image 20261012132952.png]]

A D-type edge-triggered flip-flop behaviour  is as below:
![[Pasted image 20261012132526.png]]


# Combing latches into registers 