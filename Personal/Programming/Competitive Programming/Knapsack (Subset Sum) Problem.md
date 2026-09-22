![[Pasted image 20251225224722.png]]
In this knapsack problem, there is a standard way to implement this approach using bitsets and dynamic programming. The time complexity will be $N$ - the size of the subset and $W$ and the value of the given target weight.

Let's go through the solution as if we were using a boolean array. Afterwards we will implement a few changes to use bitsets.

Let's take the case for when $W=7$ and $N = 2

Firstly create a boolean of size $N$ and initialise the first element in the boolean array to true, and everything else false. Call the boolean array $can$

In each index ,$i$ inside the boolean array, $can[i]$ corresponds to whether we can get a subset with its sum equal to $i$

![[Pasted image 20251225225309.png]]

Starting from the first index which is true, in this case it is $0$, we check if the the element 

Let's take in the first element of 2 and call it $x$. In this case $x=2$.

So we start of from 0 in can and then jump to index 2 and mark it as true.
![[Pasted image 20251225230026.png]]

Now taking tthe second element of $x$. In this case $x=3$. So ow for each element that is true. We go to start true index starting from $0$ and then add $3$ to index and make it as true.

So in this case, we start off at $0$ and we add 3, thus $3$ gets set to true.
We then move to the next true which is 2 and we add 3, thus $5$ gets marked as true.

This overall process will represent if it possible to represent a sum from a set of size $N$ of given integers $\{x_{1},x_{2}\dots x_{N}\}$

Lastly to check if it possible, we simply check the index of $W$ is true and return if it's possible to make a sum of $W$ from the given subet.

## Implementation
![[Pasted image 20251225230529.png]]

We take the inputs $n$ and the weight $W$.

Afterwards we initialise the boolean array and set the first element $0$ to true. 

For $N$ iterations, we take an input $x$. Afterwards we work backwards
![[Pasted image 20251225230810.png]]![[Pasted image 20251226232429.png]]

With changes, it is possible to write the code below using bitsets:
![[Pasted image 20251226232552.png]]

This is because the above operation is computationally identical to computing the bitwise OR with the bits shifted to right $x$ times.
![[Pasted image 20251226232644.png]]


In the code, the bit is shift is to the left because, bitsets are indexed in reverse order in comparison to an array.
