![[Pasted image 20250918172822.png]]
![[Pasted image 20250918172852.png]]

To solve this problem you need to ensure that (n(n+2))/2 % 2 == 0 (It's even). This means that sum of the two sets must equal to (n(n+1) / 2) / 2 = n(n+1)/4.  I

f this this is the case it can be proven that a solution is possible. The solution is reached by first having all the elements in set 1 and then continually moving numbers from set 1 to set 2 such that the number removed will make the calculation of n(n+1)/4 subtract the number removed, equal to another number in the set. This process is repeated until the target value is 0 or until the target number is zero
## Implementation
A standard method of implementation is to put all of the distinct integers of the permutation of n inside set 1. Have a variable named target that will indicate the target to be searched for within the set 1. Start of by setting the target to n(n+1)/4. 