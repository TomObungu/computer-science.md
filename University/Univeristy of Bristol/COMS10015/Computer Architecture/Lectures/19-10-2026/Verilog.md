Verilog is a Hardware Description Language (HDL) used to describe or model hardware. HDLs and EDA tools help facilitate automation with respect to 
1. Simulation
2. Verification 
3. Translation

Other HDLs are VHDL, MyHDL and Chisel. 

HDLs can also help address the challenge of scale with respect to design size and complexity. 

Verilog is part of broader development workflow. Verilog can be used within the design and functional verification workchain.
![[Pasted image 20261019091623.png]]
Design and verification can be though of writing the code when developing software whereas synthesis and place and route is akin to compilation and linking. 

The place and route process involves optimisations for such e.g. Finding the most efficient way to place a wire. 

Behavioural verification involves simulating the result of the previous work chains to check if it would satisfy the real life environmental variables e.g. Will the model synchronise to the clock speed appropriately. 

After this, the next steps are actually manufacturing and testing the hardware. 

The whole point of this iterative waterfall is to minimise the chance of getting to the manufacturing stage and needing restart the design due to errors. 
# Analogy
Verilog in hardware might be seen to be analogous to C in software. ![[Pasted image 20261019092412.png]]In C, you write code to produce a program whereas in Verilog you write code to produce a model of hardware. In C you write static functions whereas in Verilog you write static modules. In C, functions are references via calls whereas modules are instantiated in Verilog. Values in C are stored in variables. Values in Verilog are carried by nets on which computation is performed by modules. "Nets" can be though of us as wires. 

# Example
Below is a translation of Verilog code to represent a module of a full adder. 
![[Pasted image 20261019093051.png]]

# Levels of abstraction
## 1. switch-level Verilog
At the lowest level, the model can be described using individual transistors. For example, this Verilog code can translate to the design of a MOSFET-based NOR gate. This gives us greatest level of control.
```Verilog
pmos( t, VDD, b );
pmos( a, t, c );
nmos( a, VSS, c );
nmos( a, VSS, b );
```
## 2. gate-level Verilog
Force the model to be described at a low-level using only primitive logic gates e.g. AND, OR, NOT. 
```Verilog
nor t(a, b, c)
```

## 3. Register Transfer Level Verilog
This syntax is similar to C but focuses on describing the model in terms of data-flow between components rather than high-level components. For example, the code below produces continous assignment driving through wire with the result of evaluating $¬( b \vee c)$. It has a form of static typing. 
```Verilog
assign a = ~(b | c)
```

##  4. Behaviour-level Verilog
At the highest level, C-style descriptions of the model use assignements, loops and conditional statements. For example, the code below sets the register equal to a result of evaluating 
```Verilog
a = ~(b | c)
```

# Wires in Verilog
Wires a form of not used to communicate values. 
1. `wire w` -> Translate to an internal 1-bit wire
2. `wire [ 3 : 0] x` represents an internal 4-bit wire vector `x`

# Values in Verilog
Values in Verilog can take on the state of 3-state logic
1. 0
2. 1
3. X -> Unknown (either 1 or 0)
4. Z -> High impedence
Values in Verilog can also be written in binary, decimal or hexadecimal, e.g.
5. `2'b10` -> A 2 bit binary literal with value $2_{10}$
6. `8'd17` -> A 8-bit decimal literal with value $17_{10}$
Values in Verilog can also 