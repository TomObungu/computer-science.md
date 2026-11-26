Register Machines are an abstract computational model. They are are theoretically attractive as they can be proved to be equivalent to Turing Machines. They also have clear analogies to FSMs. However some aspects are prevalent in that some aspects such as infinitely sized regsiters cannot be realised in practice. Furthermore register machines can be inefficient.

# In theory
An instruction is a description of a computation step. 

A register machine is specified by a finite set of registers. A program is a list of instructions of the form label : body such that the i-th instruction has Label $L_i$

A RM configuration is a tuple
$$
C = \langle I, v_0, v_1,...v_{r-1} \rangle
$$

Where $I$ is the current label and $v_j$ is the current value stored in register $R_j$

## Finite Compuations

A finite computation by some RM is captured by 
$$
\langle C_0, C_1, C_2, ... \rangle
$$
That is for a sequence of configurations such that, for $i=0$:
$$
C_i = \langle I, v_0, v_1,...v_{r-1} \rangle
$$

There are other types of Register Machines with different model e.g. Counter Machines, Random Access Machines (RAM), Random-Access Stored-Program (RASP) machines. Other models also exist in that they have different sets of valid instructions such as $L_i : R_addr \gets 0$ or a "clear" instruction. Or rather, a different instruction set all together. 


# Machine Code
The corresponding machine code : $L_{i}:R_{addr} \gets R_{addr} +1$ translates to:
$$
\begin{array}{c|c|c} \\


\end{array}{c|c|c} \\

$$