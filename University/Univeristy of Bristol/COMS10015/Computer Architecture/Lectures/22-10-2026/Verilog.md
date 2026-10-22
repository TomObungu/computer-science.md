
# High-level Modelling
## Registers
Registers are a form of net used to store values. For example
- `reg w` would be synonymous with an internal 1-bit regitser `w`
- `reg [ 3 : 0 ] x` would be synonymous with an internal 4-bit registor vector x

# Module Interfacing Rules
The rules for module interfacing within a system can be modelled as the diagram below:
![[Pasted image 20261022111221.png]]
This means that the input port:
	- Externally coming in to the system it can be a wire or a register
	- Internally within the system it must be a wire
This means that in the output port:
	- Internally it can be a wire or a register
	- Externally it must be a wire

##  Behavioural-level module Implementation
There are two modules using processes. Each process is formed from blocks of statements and each process is executed in parallel with the others once triggered. 
![[Pasted image 20261022111522.png]]

The two process types include:
- Initial - triggered only once when the module is instantiated 
- Always - triggered in a loop as long as the module is powered on 
## Sensitivity lists 
Modules can have attributes that allow triggering based on certain variables 
![[Pasted image 20261022111717.png]]

For example a module can have a tag:
- `@( x )` - This means the module is only triggered when `x` changes
- `@( posedge )` - This means the module is only triggered when `x` changes from `0` to `1`
- `@( nedgedge )` - This means that the module is only triggered when `x`changes from a `1` to a `0`.
## Procedural assignment
Procedural assignment differs from continous assignement in that must use registers as the LHS. The registers are assigned to whatever the RHS evaluates to when the statement executes.

For example in the code below, the variables `x` and `y` are instantiated and only assigned values when the `always @ ( posedge clk ) begin`

```Verilog
module foo( input wire clk)

	reg x, y;
	
	always @ ( posedge clk ) begin
		x = 1'b0:
		y = 1'b1:
	end

endmodule
```