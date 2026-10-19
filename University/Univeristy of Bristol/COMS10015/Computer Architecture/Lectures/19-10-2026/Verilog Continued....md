# Subscript operator 
Consider a case where `x = 8'b11110000` and `wire [ 7 : 0]
![[Pasted image 20261019130342.png]]

# Concatenate operator
Consider a case where `x=2'b10`,`y=1'b1`  and `z=1'b0` 
![[Pasted image 20261019130600.png]]

# Module definition
Modules are a passive of static description of a component. 
![[Pasted image 20261019130633.png]]

# Module Instantiation
Are an active of dynamic use of a component
![[Pasted image 20261019130752.png]]

# Gate-level implementation 
Describes module behaviour via primitive modules or other user defined modules. 
```Verilog
buf t0(r,x);
not t1(r,x);
nand t2(r,x,y);
nor t3(r,x,y);
and t4(r,x,y);
or t5(r,x,y);
xor t6(r,x,y);

// Multi-input variables
xor t8(r,w,x,y);
xor t9(r,w,x,y,z);
```

# Examples of low-level modelling
Below would be Verilog code for a corresponding full-adder. 
```Verilog
module fa( output wire co ,
			output wire s,
			input wire ci ,
			input wire x,
			input wire y );

wire w0 , w1 , w2;

xor t0( w0 , x, y );
and t1( w1 , x, y );

xor t2( s, w0 , ci );
and t3( w2 , w0 , ci );

or t4( co , w1 , w2 );

endmodule 
```
![[Pasted image 20261019131227.png|333]]

Below would be Verilog code for a 2 input, 1 bit multiplexer
```Verilog
module mux2_1bit ( output wire r,
					input wire c,
					input wire x,
					input wire y );

wire w0 , w1 , w2;

not t0( w0 , c );

and t1( w1 , x, w0 );
and t2( w2 , y, c );

or t3( r, w1 , w2 );

endmodule
```
![[Pasted image 20261019131504.png]]

Below would the Verilog code for a 2 input, 4-bit multiplexer. Notice that code below makes use of the user defined`mux2_1bit` module defined from above. 
```Verilog
module mux2_4bit ( output wire [ 3 : 0 ] r,
					input wire c,
					input wire [ 3 : 0 ] x,
					input wire [ 3 : 0 ] y );

mux2_1bit t0( r[ 0 ], c, x[ 0 ], y[ 0 ] );
mux2_1bit t1( r[ 1 ], c, x[ 1 ], y[ 1 ] );
mux2_1bit t2( r[ 2 ], c, x[ 2 ], y[ 2 ] );
mux2_1bit t3( r[ 3 ], c, x[ 3 ], y[ 3 ] );

endmodule
```
![[Pasted image 20261019131634.png]]

Below would be the Verilog code for a 4-bit, 1-bit multiplexer. In this case, the implementation still uses the user defined `mux2_1bit` from above
```Verilog
module mux4_1bit ( output wire r,
					input wire c0 ,
					input wire c1 ,
					input wire w,
					input wire x,
					input wire y,
					input wire z );

wire w0 , w1;

mux2_1bit t0( w0 , c0 , w, x );
mux2_1bit t1( w1 , c0 , y, z );
mux2_1bit t2( r, c1 , w0 , w1 );

endmodule
```
![[Pasted image 20261019131753.png]]

# User-Defined Primitives
An advantage of Verilog is a concept known as UDPs. In Verilog, it is possible to write a primitive type that has a truth table that is equivalent to a truth table that is wanted to be computed. The Verilog code will produce the same output as the truth table on the left:
```Verilog
primitive mux2_1bit ( output r,
						input c,
						input x,
						input y );
	table
	 0 0 ? : 0;
	 0 1 ? : 1;
	 1 ? 0 : 0;
	 1 ? 1 : 1;
	endtable

endprimitive
```

![[Pasted image 20261019132232.png]]

# Register Transfer Level (RTL) modules
Register transfer levels allow continuous assignments. The LHS must be a wire or wire vector, whereas the RHS can contain many C-style operators. Beware that if this setup is continuous it means that it is sequential the stepwise logic code. The code below
```Verilog
assign r = ( x | y) & z
```
would be map to such code below:
```Verilog
or t0(w, x, y);
and t1(r, w, z)
```
The code above would map the logic gates below:
![[Pasted image 20261019132901.png]]

## Reduction operator
Consider a case where wire `wire [ 3 : 0 ] x`.  The reduction expression can be expressed as a sequential application of the XOR function for each element in the wire
![[Pasted image 20261019133235.png]]

# Tenary operator
The tenary operator can allow inline if-else statements
Consider the case where `wire [ 3 : 0 ] x`, `wire [ 3 : 0 ] y` and `wire c`. The statement below
```Verilog
c ? y : x
```
Maps to such 
![[Pasted image 20261019133554.png]]

# Registers (Sequential Logic)
Register within Verilog are a form of net used to store values that retain state. A register can be seen as buffer to store values. A register can be instantiated using the `reg` command.
```Verilog
reg w
```
An internal 4-bit registor vector x can be defined as below
```Verilog
reg [ 3 : 0] x
```
