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
Verilog in hardware might be seen to be analogous to C in software. ![[Pasted image 20261019092412.png]]In C, you write code to produce a program whereas in Verilog you write code to produce a model. 