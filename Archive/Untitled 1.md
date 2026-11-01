# Example 
In C there are representations
$$
\text{unsigned char} \approxeq \text{uint8\_t} \mapsto \{ 0, \dots, +2^{8}-1\} \\ \\
\text{(signed) char} \approxeq \text{uint8\_t} \mapsto \{ -2^{7}, \dots, +2^{7}-1\} 
$$For unsigned char , the upper and lower bounds are:
$$
\begin{gather*}
11111111 \mapsto 1 \cdot 8^{0} + 1 \cdot 8^{1} + 1 \cdot 8^{2} 1 \cdot 8^{3} + 1 \cdot 8^{4} + 1 \cdot 8^{5} + 1 \cdot 8^{6} + 1 \cdot 8^{7} + 1 \cdot 8^{8} = +255_{10} \\ \\ 00000000 \mapsto 0 \cdot 8^{0} + 0 \cdot 8^{1} + 0 \cdot 8^{2} 0 \cdot 8^{3} + 0 \cdot 8^{4} + 0 \cdot 8^{5} + 0 \cdot 8^{6} + 0 \cdot 8^{7} + 0 \cdot 8^{8} = +0_{10}
\end{gather*}
$$
For  a signed char, the bounds are slightly different. In that the there negative values:
$$
01111111 \mapsto (-1)^{0} \cdot (1 \cdot 8^{0} + 1 \cdot 8^{1} + 1 \cdot 8^{2} 1 \cdot 8^{3} + 1 \cdot 8^{4} + 1 \cdot 8^{5} + 1 \cdot 8^{6} + 1 \cdot 8^{7} + 1 \cdot 8^{8} = +255_{10} \\ \\
00000001 \mapsto (-1)^{0} \cdot (1 \cdot 8^{0} + 1 \cdot 8^{1} + 1 \cdot 8^{2} 1 \cdot 8^{3} + 1 \cdot 8^{4} + 1 \cdot 8^{5} + 1 \cdot 8^{6} + 1 \cdot 8^{7} + 1 \cdot 8^{8} = +1_{10} \\ \\
00000000 \mapsto (-1)^{0} \cdot (1 \cdot 8^{0} + 1 \cdot 8^{1} + 1 \cdot 8^{2} 1 \cdot 8^{3} + 1 \cdot 8^{4} + 1 \cdot 8^{5} + 1 \cdot 8^{6} + 1 \cdot 8^{7} + 1 \cdot 8^{8} = +0_{10} \\ \\
10000001 \mapsto (-1)^{0} \cdot (1 \cdot 8^{0} + 1 \cdot 8^{1} + 1 \cdot 8^{2} 1 \cdot 8^{3} + 1 \cdot 8^{4} + 1 \cdot 8^{5} + 1 \cdot 8^{6} + 1 \cdot 8^{7} + 1 \cdot 8^{8} = -1_{10} \\ \\
 11111111 \mapsto (-1)^{0} \cdot (1 \cdot 8^{0} + 1 \cdot 8^{1} + 1 \cdot 8^{2} 1 \cdot 8^{3} + 1 \cdot 8^{4} + 1 \cdot 8^{5} + 1 \cdot 8^{6} + 1 \cdot 8^{7} + 1 \cdot 8^{8} = -127_{10} 
$$
# Left shift

# Right Shift