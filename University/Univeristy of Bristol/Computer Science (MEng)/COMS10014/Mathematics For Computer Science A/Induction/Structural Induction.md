Whenever you have a recursively defined data type, then you can do proofs by induction over the structure of the data type. 

For example, consider the following rules for building term strings:
1. T1 is an integer term, called a value term. 
2. A variable is a term 
3. IF X, Y are terms then so are $X+Y$, $X-Y$ and $X \times Y$. These are called operation terms. 
4. If $X$ is a term then so is $(X)$

From this structure we can prove that every term string has balanced brackets. Let $T$ be any term.

1. If $T$ is a value term, then $T$ contains no brackets at all
2. If $T$ is a variable term, then $T$ still contains no brackets so brackets are still balanced
3. If $T$ is an operation term, then our induction assumption is that the subterms $X$, $Y$ both have balanced brackets. If $X$ has $a$ opening brackets and $Y$ has $b$ opening brackets then $T$ has $a+b$ opening and closing brackets
4. If $T$ is a bracket term, then out induction assumption is that the subterm $X$ has balanced brackets; Let the number of opening and closing brackets in $X$ be $n$. Thus $T$ has $n+1$ opening and closing brackets.

For another example, we prove that every term built according to these rules has one more leaf term than it has operation terms. For any term $T$.

1. If $T$ is a value term, then it contains $m=1$ value terms (itself) and $n=0$ operation terms and $m=n+1$ as required
2. If $T$ is a variable term, then $m=1$, $n=0$, $m=n+1$ as above
3. If $T$ is an operation term with two children $X$ and $Y$ let $m_{x}$, $n_{x}$ and $m_{y}$ and $n_{y}$ be the numbers of the leaf and operation terms in $X$, $Y$ respectively. Our induction assumption is that $m_{x}=n_{x} + 1$ and $m_{y}=n_{x} + 1$
4. If $T$ is a bracket term with a child term $X$ with $m$, $n$ and leaf operation terms respectively. 
# Examples

---
# Well-Ordering for Structural Induction
