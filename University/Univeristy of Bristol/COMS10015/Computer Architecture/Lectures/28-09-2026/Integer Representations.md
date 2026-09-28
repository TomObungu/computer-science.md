Conceptually we can say that the decimal $123$ is basically a sequence of digits
$$
123 \equiv \langle 3, 2, 1 \rangle
$$
Given a bit is a single binary digit, a byte is an 8-element sequence of bits and a word is a $\omega$-element of sequence of bits. 
$$
01111011 \equiv \langle 1,1,0,1,1,1,1,0 \rangle
$$
What does these elements mean? Well it possible to define them as anything that we want. 
# Mapping
When mapping, we need a concrete representation that can be written down and a mapping that yields the correct value and is consistent in both directions. 
$$
\underbrace{ \hat{X} }_{ \text{The representation of X} } \mapsto \underbrace{ X }_{ \text{The value of X} }
$$

Given a literal such as $X = 11111011$. $X$ can be interpreted in two ways. It can be interpreted into either little-endian ordering or big-endian ordering:
$$
\begin{gather*}
\hat{X}_{LE} = \langle X_{1},X_{2},X_{3},X_{4},X_{5},X_{6},X_{7},X_{8},X_{1},  \rangle = \langle 1,1,0,1,1,1,1,\rangle
\\ \\
\hat{X}_{BE} = \langle 1,1,1,1,0,1,1,\rangle
\end{gather*}
$$
Following the idea of vecotrial Boolean functions, given an n-element bit-sequence $X$ and an $m$-element bit-sequence $Y$, it possible to clarify to overload operators to write the variable $X$ if its indexed within a data structure with an index of $i$ . For example consider the operations for 

# Hamming Weight
The Hamming Weight is the number of bits within a binary sequence $X$ that are equal to $1$. That is the number of times $X_{i}=1$. This can be expressed as:
$$
HW(X) = \sum_{i=0}^{n-1} X_{i}
$$
# Hamming distance
The Hamming distance between $X$ and $Y$ is the number of bits in $X$ that differ from the corresponding bit in $Y$ i.e the number of times that $X_{i} = Y_{i}$. This can be expressed as:
$$
\sum_{i=0}^{n-1} = X_{i} \oplus Y_{i}
$$

# Radix-$b$ Expansions
A propositional number system expresses the value of a number $x$ using a base$-b$ expansions.
$$
\begin{gather*}
\hat{x} = \langle \hat{x}_{0}, \hat{x}_{1},\dots,\hat{x}_{n-1} \rangle \\ \\
\mapsto \\ \\
 = \pm \sum_{i=0}^{n-1} \hat{x}_{i} \dot{ b^{i}}
\end{gather*}
$$
Where each $\hat{x}_{i}$ represents one of the n digits taken from the set $X = \langle 0,1,1\dots \rangle$ and $b$ represents some weighted power base. 

## Value of $b>10$
For $b>10$,, we can't express $\hat{x}_{i}$ using a single Arabic numeral itself. For $b>10$. Singlular letters are used instead.


## Example 
Consider an example where $b=10$. This means that
$$
x \in X = 10 = \langle 0, 1,\dots, 10 - 1 = 9 \rangle 
$$
Thus showing the summation sequence gives:
$$
\begin{gather*}
\hat{x} = \langle \hat{x}_{0}, \hat{x}_{1},\dots,\hat{x}_{n-1} \rangle \\ \\
\mapsto \\ \\
 = \pm \sum_{i=0}^{n-1} \hat{x}_{i} \dot{ b^{i}}
\end{gather*}
$$
