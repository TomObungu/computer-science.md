Conceptually, we can say that the literal $123$ is basically just a sequence of digits.
$$
123 \equiv \langle{3 ,2, 1} \rangle
$$
It is up to us as the user, what these decimal digits represent. 
# Grouping
Some bit-sequences are given special names depending on their length. For example for base 2 binary.

- A bit is a single binary digit i.e $0$ or $1$
- A nybble is a 4-element binary
- A byte is an 8-element sequence of bits

- A word is a $w$-element sequence of bits
- A half-word is a $\frac{w}{2}$-bit sequence
- A doubl- word is a $w \cdot 2$-bit sequence
- A quad-word is a $w \cdot 4$-bit sequence

$$
01111011 \equiv \langle 1,1,0,1,1,1,1,0 \rangle
$$
# little-endian
A little-endian ordering is where we read bits in a literal form from right-to-left
$$
\hat{X}_{LE} = \langle X_{0}, X_{1}, X_{2}, X_{3}, X_{4}, X_{5}, X_{6} \rangle =  \langle 1,1,0,1,1,1,1 \rangle 
$$
# big-endian 
A big-endian ordering is where we read bits in a literal form from left-to-right
$$
\hat{X}_{BE} = \langle X_{6}, X_{5}, X_{4}, X_{3}, X_{2}, X_{1}, X_{0} \rangle =  \langle 1,1,1,1,0,1,1 \rangle 
$$

# Least-Significant Bit (LSB) and Most-Significant Bit (MSB)
Given a bit-sequence X, the LSB and MSB are those in X which have the least and most significance. They have the least and most impact on, the value it represents. 

# Overloading
It is possible to write $R = \ominus X$ and $R_{i = X \ominus Y}$ as  $R_{i} = \ominus X_{i}$ and $R_{i} = X_{i}\ominus Y_{i}$
for $\ominus \in \{\land, \lor, \oplus\}$. Note for $R = \ominus X$, it is $0 \leq i <n$ and for $R_{i} = X_{i}\ominus Y_{i}$ it is $0 \leq i <n=m$, where if $n\neq m$, we pad either $X$ or $Y$ with $0$ until the $n=m$.

---
# Hamming Weight 
The Hamming weight of $X$ is the number of bits that are equal to $1$ i.e, the number of times $X_{i}=1$. 
$$
HW(X) = \sum^{n-1}_{i =0} X_{i}
$$

# Hamming Distance
The Hamming distance between $X$ and $Y$ is the number of bits in $X$ that differ from the corresponding bit in $Y$. The number of times $X_{i} \ne Yi$. 
$$
HD(X,Y) = \sum^{n-1}_{i=0} X_{i} \oplus Yi = HW (X \oplus Y)
$$
# Example 
Given $X=\langle 1,0,0,1 \rangle$ and $Y = \langle 0,1,1,1 \rangle$, we find that $HW(X) = \sum ^{n-1}_{i=0} X_{i}=1+0+0+1=2$ and $HD(X,Y)=\sum ^{n-1}_{i=0} X_{i} \oplus Y_{i} = HW(X \oplus Y) = (1 \oplus 0) + (0 \oplus 1)\dots = 1 + 1 +1 + 0 = 3$

---
# Positional Number System
A positional number system expresses the value of a number $x$ using a base-$b$ (or radix-$b$) expansion. 
$$
\begin{gather*}
\hat{x} = \hat{x} \langle \hat{x}_{0}, \hat{x}_{1},\dots, \hat{x}_{n-1}  \rangle \mapsto x \\ \\
= 
\pm \sum_{i=0}^{n-1} \hat{x}_{i} \cdot b^{i}
\end{gather*}
$$
Where each $\hat{x}_{i}$ is one of $n$ digits taken from the digit set $X = \{0,1, \dots,b-1\}$ and is "weighted" by some pwer of the base $b$.

Beware that for $b>10$, we cannot express $\hat{x}_{i}$ using a single Arabic numeral. for $b=16$ (Hexadecimal) for $10 \leq \hat{x}_{i} \leq 16$, letters are used. $A \mapsto 10$, $B \mapsto 11$, $D \mapsto 12$, $C \mapsto 13$,$D \mapsto 14$, $E \mapsto 15$, $F \mapsto 16$.

# Example : Octal Numbers
Consider the case of octal numbers. In this case $b=8$ and $x_{i} \in X \{0, 1, \dots, 8 - 1=7\}$ and we want to represent the octal number $\hat{x} = 173$ in base 10 decimal. 
$$
\begin{gather*}
\hat{x} = 173 = \langle 3, 7, 1 \rangle \mapsto 
x \\ \\
= \sum_{i=0}^{n-1} \hat{x}_{i} \cdot 8^{i} \\ \\
= 3 \cdot 8^{0} + 7 \cdot 8^{1} + 1 \cdot 8^{2} \\ \\
= 3 + 56 + 64 \\ \\
= 123_{(10)}
\end{gather*}
$$
---
# Standard Integer Representations
We want to represent elements of $\mathbb{Z}$ but it is an infinite set and so far we've ignored the issue of sign. 
## Unsigned Integer 
An unsigned integer can be represented in $n$ bits by using the natural binary expansion.
$$
\begin{gather*}
\hat{x} = \langle \hat{x}_{0}, \hat{x}_{1},\dots, \hat{x}_{n-1} \rangle  \mapsto x  \\ \\
= \sum^{n-1}_{i=0} \hat{x}_{i} \cdot 2^{i} 
\end{gather*}
$$
For $\hat{x} \in\{0,1\}$. This yields
$$
0 \leq x \leq 2^{n} - 1
$$
## Signed Integers
A signed can be represented in $n$ bits using the sign-magnitude approach: $1$ bit is reserved for the sign. 
$$
\begin{gather*}
\hat{x} = \langle \hat{x}_{0}, \hat{x}_{1},\dots, \hat{x}_{n-1} \rangle  \mapsto x  \\ \\
= (-1)^{\hat{x}-1}\cdot \sum^{n-1}_{i=0} \hat{x}_{i} \cdot 2^{i} 
\end{gather*}
$$
For $\hat{x} \in\{0,1\}$. This yields
$$
-2^{n-1} \leq x \leq +2^{n-1}-1
$$
# Left Shift
A left shift of some $x$ by $y$ digits is equivalent to multiplication by $b^{y}$. For taking the standard $b=2$.
$$
\begin{gather*}
x \times 2^{y} = \left( \sum ^{n-1}_{i=0} \hat{x}_{i} \cdot 2^{i} \right) \times 2^{y} \\ \\
= \sum ^{n-1}_{i=0} \hat{x}_{i} \cdot 2^{i+y} \\ \\
= x \ll y
\end{gather*}
$$

# Right Shift
A right-shift of some $x$ by $y$ digits is equivalent to division by $b^{y}$
$$
\begin{gather*}
x / 2^{y} = \left( \sum ^{n-1}_{i=0} \hat{x}_{i} \cdot 2^{i} \right) / 2^{y} \\ \\
= \sum ^{n-1}_{i=0} \hat{x}_{i} \cdot 2^{i-y} \\ \\
= x \gg y
\end{gather*}
$$
