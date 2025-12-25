![[Pasted image 20251225224722.png]]
In this knapsack problem, there is a standard way to implement this approach using bitsets and dynamic programming. The time complexity will be $N$ - the size of the subset and $W$ and the value of the given target weight.

Let's go through the solution as if we were using a boolean array. Afterwards we will implement a few changes to use bitsets.

Firstly create a boolean of size $N$ and initili
