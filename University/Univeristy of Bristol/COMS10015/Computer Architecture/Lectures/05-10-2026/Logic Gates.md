From the wise words of Claude Shannon:
$$
\begin{gather*}
V_{ss} = 0V \approx GND |= 0 \\ \\
V_{dd} = 5V |= 1
\end{gather*}
$$
and assume the power rails are everywhere. This forms a pull-up network of P-MOSFET transistors connected to $V_{dd}$ and a pull-down network of a N-MOSFET transistor connected to $V_{ss}$. The functionality can be abstractly represented using logic gates using a truth table such as:

| $x$ | $y$ |
| --- | --- |
| $0$ | $1$ |
| $1$ | $0$ |
It is easier to derive the logic gates for NAND and NOR using transistors. Remember that NAND and NOR are universal Boolean functions - thus from them, every other Boolean function such as AND,OR can be composed from them. It is often more efficient to make NAND and NOR circuits than AND and OR circuits directly. 

The inversion of the NOT gate is called a "buffer". Computationally this may not have much value, however it is still possible to think about them on higher levels of abstraction. 

# Physical Limitations
## Delay
Wire delay - The time taken for current to move through the conductive wires from one to another
Gate delay - The time taken in each gate to switch between connected and unconnected states. 

Often times the wire delay is greater than wire. 

The critical path is the path in which there is the longest sequential delay between and input and output. That is, it is the path that has the largest delay from the sum of the combinations of the circuits. 

In reality the idealised instantaneous square response is not realistic. A more curved response between logic levels is realistic. 

## Static time representation
In abstract representations of logic gates, the out values are worked out without considering the time of computation. 

## Dynamic time representation 
Consider the time delays for the associated logic gates

NOT -> 10ms
AND -> 20ms
OR -> 20ms

This means there will be a variation of results of the logic gates depending on the time interval. 

The critical path will be the sum of the times of delay for each logic gates. In this case it would be 50ms. In this case it would be 50ms. Crucially there are some points in time where the output is actually incorrect.

## Extra state of $\mathbb{Z}$  
The value of $\mathbb{Z}$ would represent a value of high impedance. The idea is to allow a wire to be "disconnected" per say. 

## Fan-in and fan-out





