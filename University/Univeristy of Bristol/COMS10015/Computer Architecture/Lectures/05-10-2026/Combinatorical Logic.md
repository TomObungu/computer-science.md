Combinatorical logic is viewed as continous; changing the input continously produces a changing output. There is less of an emphasis on sequential process. Furthermore, the output is a function of input only. 

Combinatorical logic is on the basis of special-purpose design patterns, building blocks and general purpose derivation. 

# Special Purpose Design Patterns
## Reuse
If within a circuit you compute
$$
r = x \land y
$$
and elsewhere you also compute
$$
r' = x \land y
$$
Then it is possible to replace the two AND gates with the first instance of the already computed result:
$$
r = r'
$$
# Decomposition 
Given an $n$-input function with $m$ outputs. It is possible to decompose the function in terms of smaller and simpler functions

# Independent replication
It is possible to take a problem solved and replicate the function on each index of $r_{i}$. 

# Dependent replication 
It is possible to compute multiple inputs. The outcomes of each computation are combined. 

# Selection
Such special purpose building blocks include:
1. A multipliexer
	- Has $m$ inputs
	- Has one output
	- Uses a $\log_{2}(m)$ bit control signal input to choose which input is connected to the output
2. A demultiplexer
	- Has 1 input
	- Has $m$ outputs
	- Uses a $\log_{2}(m)$ bit control signal input to choose which output is connected to the input. 

## Multiplexer Analogy in C
The C `switch` statement can show the behaviour of a multiplexer
```C
switch(c) {
	case 0: r = x
	case 1: r = y
}
```
Below is also an example behaviour of a demultiplexer 
```C
switch(c) {
	case 0: r_0 = x
	case 1: r_1 = x
}
```

