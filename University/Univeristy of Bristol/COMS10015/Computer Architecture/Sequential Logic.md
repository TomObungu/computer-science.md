Consider the problem of designing a $n$-bit counter. That is a component that outputs the values of $0$ until $2 ^{n-1}$ sequentially. That is some free running circuit implementation that prints:
$$
0, 1,2,3\dots 2^{n-1}
$$
The term free running that circuit repeats the same process until say there is a power outage failure. If it is free running the circuit will wrap around back to one once it reaches $2^{n}-1$.
$$
0, 1,2,3\dots 2^{n-1}, 0, 1\dots
$$
## Ripple Carry Adders
Ripple carry adders with $n$ bits can compute the values of $x+y$. However fundamentally, there is a problem in that there is no way in which the standard ripple carry adder can **hold** the value of $r$. The adder needs to be designed in such a way that it can compute
$$
r \leftarrow r+1
$$
How there is a problem in that the value of $r_{0}$ cannot be stored and that even if the value of $r_{0}$ could be stored. There is no way to control the output to settle and synchronise before it is used again as an input. 

The solution to this is sequential logic design - the output of a function plus any state, viewed as discrete. Sequential logic contains the 
1. Synchronisation of components using clocks
2. Components that maintain state using latches, flip flops and registers
3. Mechanism for computational steps

# Clocks
A lock is a signal that oscillates between $1$ and $0$. The usage of clocks can be used for synchronisations and triggering of inputs. 

![[Pasted image 20261012092050.png]]

Clocks signals are generator either by a clock generator or an externally supplied input. 

The clock frequency must be fast enough to satisfy design goals but slow enough to cope with the critical path of a given step. If the clock frequency is faster than the critical path than the step then the next step will begin without the outputs being ready to be processed. 