The basic thing you can do when you have element and set is this element in the set?
# Notation
If $x$ is an element and $S$ is a set, then the notation is $x \in S$, if $x$ is in $S$. Otherwise $x \notin S$. 

We can write sets by listing their elements between curly braces, thus $S = {2,3}$ is the set containing two elements $2$, $3$ so $(2 \in S)$ but $4 \notin S$

# Set Equality
Sets are completely defined by their elements, that is, two sets are equal only if they contain the same elements. As a formula this can be written as:
$$
\forall X,Y : \text{sets} . (X = Y \leftrightarrow  . ( a\in X \leftrightarrow  a \in Y))
$$
## Properties of Set Equality
- $\{2,3\}$ and $\{3,2\}$ are the same set but written in different ways. 
- $\{2,3,3\}$ is the same set as $\{2,3\}$, a set cannot contain an element more than once. 
- However $\{2,3\}$ and $\{\{2\},3\}$ are not the same. The former set contain the numbers 2,3 and the latter is a set containing the number 3 and the set  containing the number 2 as elements. 

## Empty Set
The empty set is the set with no elements. We write it either $\{\}$ or $\phi$. As formula:
$$
\forall a.a \in \phi
$$
# Set Operations
We can combine two sets to make a new one.  For two sets $X,Y$. 
The union $X \cup Y$ is the set of all elements in either sets of the sets, or both
$$
\forall a.(a \in X \cup Y \leftrightarrow  a \in X \vee a \in Y)
$$
The intersections $X \cap Y$ is the sets of all elements in both sets, as a formula
$$
\forall a . (a \in X \cap Y \leftrightarrow  a \in X \wedge a \in Y )
$$
The difference $X \setminus Y$ is the set of all elements in both sets, as a formula
$$
\forall a . (a \in X \setminus Y \leftrightarrow  a \in X \wedge a \notin Y)
$$

The similarity in shapes between $\vee$ and $\cap$ and between $\vee$ and $\cup$ is intentional. Some books write $X-Y$ for set difference instead of $X\setminus Y$

# Universe of a set
The universe of a set is defined as $\mathcal{U}$, such as the integer or real numbers $\mathbb{Z}$ or $\mathbb{R}$. Then we can define a set's complement $\bar{X}  = \mathcal{U} \setminus X$. 

Note that without a universe, $\{a | a \notin X\}$ is not a valid term as a set restriction needs to start with a set, but $\{a \in \mathcal{U} | a \notin X \}$. In this case $\mathcal{U}$



