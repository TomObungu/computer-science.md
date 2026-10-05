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

