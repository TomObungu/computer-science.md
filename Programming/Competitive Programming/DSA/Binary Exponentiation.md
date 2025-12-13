Binary exponentiation is a trick which allows calculation of $a^{n}$ using $O\log(n)$ multiplications instead $O(n))$ multiplications.

It can be used with any operations that have the property of associativity:
$$
(X \cdot Y)\cdot Z= X(Y \cdot Z)
$$

Iterative method of binary exponentiation to achieve exponentiation in $O\log(b)$ where $b$ is the exponent in $a^{b}$:
```C++
int power(int a, int b){
	int result = 1;
	while(b > 0){
		if(b%2 == 1) result *= a
		a *=a;
		b /= 2;
	}
	return result;
}
```
