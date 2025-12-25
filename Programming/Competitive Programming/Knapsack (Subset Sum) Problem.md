![[Pasted image 20251225224722.png]]
In this knapsack problem, there is a standard way to implement this approach using bitsets and dynamic programming. The time complexity will be $N$ - the size of the subset and $W$ and the value of the given target weight.

Let's go through the solution as if we were using a boolean array. Afterwards we will implement a few changes to use bitsets.

Let's take the case for when $W=7$ and $N = 2

Firstly create a boolean of size $N$ and initialise the first element in the boolean array to true, and everything else false. Call the boolean array $can$

In each index ,$i$ inside the boolean array, $can[i]$ corresponds to whether we can get a subset with its sum equal to $i$

![[Pasted image 20251225225309.png]]

Starting from the first index which is true, in this case it is $0$, we check if the the element 

Let's take in the first element of 2 and call it x. In this case $x=2$.

So we start of from 0 in can and then add 
![[Pasted image 20251225230026.png]]