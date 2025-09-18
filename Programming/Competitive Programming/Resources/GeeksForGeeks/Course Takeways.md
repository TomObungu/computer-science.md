https://www.geeksforgeeks.org/problems/reverse-squared-sum/0
Using i to negate the sign of a sum using a for loop:
```C++
ll answer = 0;

for(int i = (n - 1); i > -1; i--) {

short x = nums[i];

answer += (i % 2 == 0) ? (-(x*x)) : (x*x);

}

cout << ((n % 2 == 1) ? -answer : answer)<< '\n';
```
---
