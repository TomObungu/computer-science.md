The HP-35 Calculator was released in 1972 and discontinued in 1975. 

The HP-35 model can be abstracted to show the concepts of FSM + arithmetic. These build up a calculator and show relation to micro-processors. 

The FSM of the calculator can be shown with the input alphabet $X_{i} \in\Sigma$. These represent the operands and digits on the keypad. Secondary the calculator contains transition functions $\delta$ and $\omega$. As well as that the states of the computation are held in $Q$. The letters of $Q \in S$. 

The computations of the next state are given as $Q'=\delta(Q,X_{i})$. The result is then outputted with the output functions $R_{i}=\omega(Q,X_{i})$. The output is the outputted on screen such that $R_{i}\in \Gamma$.

# Algorithm 
1. The first steps of the algorithm include showing the contents of the register X. The digits are $V$  such that $V\in\{0,1,\dots , 9\}$. For each digit position $X'$ i.e tens, hundreds, thousands..., the digit is shown to be $X' \gets 10 \cdot X+V$.
2. The HP-35 contains 4 registers $X$, $Y$, $Z$ and $T$. The data layout of these registers can be show as a stack. The computations are performed with the binary operator $\odot$.  The registers $Y,Z,T$ are such that $Y'\gets Y$, $Z'\gets Z$ and $T'\gets T$.
3. On the case of pressing the 'CLR' button, the registers $X$


# Notation
The HP-35 uses reverse polish notation which is known as post-fix notation. The operands and digits are given as:
$$
19 \quad 5 \quad - \quad 1 \quad 2 \quad + \quad \times
$$
This notation is attractive as it is unambiguous without parentheses and can be easily evaluated as a stack. This evaluation can be computed as per $\delta$ and the output $\omega$ can transition the output to more readable in-fix notation. 


# Interface 
Consider 
$$
19 \quad 5 \quad - \quad 1 \quad 2 \quad + \quad \times
$$

# Implementation 
The internal composition of the HP-35 can be composed of a 2-phase clock for synchronisation, the arithmetic and register unit (A&R). The ROM unit and the C&T unit for control signals to tell what the A&R unit should compute. There is a lot of parallel with the Von-Neumann CPU architecture known today. 
![[Pasted image 20261119113416.png]]

# Arithmetic and Register Unit (A&R)

## Arithmetic

## Register
The register part of the contains of the A&R unit consists of the current value of the register $X$, a large multiplexer that has multiple branches to map the next state $X'$. The multiplexer contains control signals from the C&T unit to select the branch. The design uses latches as it contains a two phase clock. The design is implemented for each register $Y$,$Z$,$T$ and $S$.
![[Pasted image 20261119114038.png]]