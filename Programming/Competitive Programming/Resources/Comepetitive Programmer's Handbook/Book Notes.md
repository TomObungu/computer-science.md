
# 1.2
It is possible to take in input all at once using seperate `<<` such that  when using cout:
```C++
int a, b; 
string x; 
cin >> a >> b >> x;
```
 i.e the input
```
123 456 monkey
```
is the same taking in the input as
```
123       456 
monkey
```

---
It is possible to store the input as a .txt file and then output it to a separate file for certain contests.
```C++
freopen("input.txt", "r", stdin); 
freopen("output.txt", "w", stdout);
```
---
C++ template:
```C++
#include <bits/stdc++.h> 
using namespace std; 
int main() { 
// solution comes here 
}
```


# 1.3
int -> -2.10^31 .. 2.10^31 - 1 ( -2.10^9 .. 2.10^9 -1   \[32 bits]
unsigned -> -2.10^31  ( 2.10^9 ) 
long long -> −2.10^63 . . . 2.10^63 − 1 ( −9 · 10^18 . . . 9 · 10^18)

## Common mistake
```C++
int a = 123456789; 
long long b = a*a; 
cout << b << "\n"; // -1757895751
```
both numbers in the expression a * a are of type int and the result is also of type int. Because of this, the variable b will contain a wrong result. 

an be solved by changing the type of a to long long or by changing the expression to (long long)a * a


Still, it is good to know that the g++ compiler also provides a 128-bit type __int128_t with a value range of −2127 . . . 2127 − 1 or about −1038 . . . 1038.


## Modular Arithmetic
Sometimes, the answer to a problem is a very large number but it is enough to output it ”modulo m”, i.e., the remainder when the answer is divided by m (for example modulo 10^9 + 7)

The idea is that even if the actual answer is very large, it suffices to use the types int and long long

An important property of the remainder is that in addition, subtraction and multiplication, the remainder can be taken before the operation: 

- ( a + b) % c = ( ( a % c ) + ( b % c ) ) % c
- ( a * b) % c = ( ( a % c ) * ( b % c ) ) % c
- ( a - b) % c = ( ( a % c ) - ( b % c ) ) % c

Thus, we can take the remainder after every operation and the numbers will never become too large

However modulo divison is distributive overn +,- and * but not division

The result of ( a % b ) will always be less than b. i.e (a%b) <= (b-1)

### Why 10^9 + 7
1. 10^9 + 7 is prime and is large enough to fit the largest integer data type
2. Taking the mod a prime number will generally produce a spaced result
3. First 10 digit prime, infact any primte number less than 2^30 will fine in order to prevent oflow

## Using modulo to compute large numbesr
ue to the size of variable limitations, we **perform modulo M at each intermediate stage** so that range overflow never occurs.

For example if we ran this code:
```
a = 145785635595363569532135132
b = 3151635135413512165131321321
c = 999874455222222200651351351
m = 1000000007
Print (a*b*c)%m.
```

In most languages like c++ where the maximum size of an integer is 2^64 - 1. a * b * c will not fit and thus the system will drop some significant digits and will output an incorrect answer:

The correct answer is 
```
(a*b*c)%m = 798848767
```

Using modulo at each intermediate stage will allow the correct answer to prevent integer overflow

```
Take modulo at each intermediate steps:
i = 1
i = (i*a) % m    // i = 508086243
i = (i*b) % m    // i = 144702857
i = (i*c) % m    // i = 798848767
i = 798848767
```

Thus whenever asked to computer large numbers with the modulo m 10^9 + 7 then declare m as a variable and % m on each intermediate step

### Wrong approach
```C++
unsigned long long factorial(int n)
{
    const unsigned int M = 1000000007;
    unsigned long long f = 1;

    for (int i = 1; i <= n; i++)
        f = f * i;  // WRONG APPROACH as
                    // f may exceed (2^64 - 1)

    return f % M;
}

// This code is contributed by Shubham Singh
```

### Correct approach
```C++
unsigned long long factorial(int n)
{
    const unsigned int M = 1000000007;

    unsigned long long f = 1;
    for (int i = 1; i <= n; i++)
        f = (f*i) % M;  // Now f never can
                        // exceed 10^9+7
    return f;
}

// This code is contributed by Shubham Singh
```

This is due to (a + b + c) % M =  ( ( ( a + b ) % M ) + c ) % M.

## Negative modulo
In practice, the modulo of a negative number will return a negative number i.e 
```
-5%3 = -2,
```

If the result of % should be in the range 0 n - 1 then -5%3 = 1. So for this convert it into a positive modular equivalent.

```C++
int mod(int a, int m)
{
    return (a % m + m) % m;
}

// This code is contributed by 
// Shubham Singh(SHUBHAMSINGH10)
```

### MMI
https://www.geeksforgeeks.org/dsa/modulo-1097-1000000007/
The multiplicative inverse of a number y is z if (z * y) == 1

Dividing a number x by another number y is the same as multiplying x with the multiplicative inverse of y.

/ y == x * y^(-1) == x * z (where z is multiplicative inverse of y).

In mathematics, the modular multiplicative inverse of an integer 'a' is an integer 'x' such that the product ax is congruent to 1 with respect to the modulus m.

ax=1(modm)

```
If M = 7, the MMI of 4 is 2 as (4 * 2) %7 == 1,
If M = 11, the MMI of 7 is 8 as (7 * 8) % 11 == 1,
If M = 13, the MMI of 7 is 2 as (7 * 2) % 13 == 1.
```

**Etended Euclidean algorithm** and the second using **Fermat’s Little Theorem**.

## Precision errors
this technique can be used whilst subtracting floats by checking if the difference is smaller than some $\varepsilon$ 
```C++
if (abs(a-b) < 1e-9) 
{ // a and b are equal 
}
```

## Representing integers using float
For example, using double, it is possible to accurately represent all integers whose absolute value is at most 2^53.

floating point types in competitive programming are the 64-bit double and, as an extension in the g++ compiler, the 80-bit long double. In most cases, double is enough, but long double is more accurate.
## 1.4

# Macros
```C++
typedef long long ll;
```

```C++
typedef vector<int> vi; 
typedef pair<int,int> pi;
```

```C++
#define F first 
#define S second 
#define PB push_back 
#define MP make_pair
```

# 1.5
Sum of all n up to n = 
$$
\frac{n(n + 1)}{2}
$$

Sum of $x^{2}$ up to n = 
$$
\frac{n(n+1)(2n+1)}{6}
$$
Sum of arithmetic progression = 
$$
\frac{n(a+b)}{2}
$$
Sum of  a geometric progression with constant 2 e.g.
3,6,12,24
$a+ak+ak^{2}$
$$
\frac{bk-a}{2}
$$
Where a is the first number and b is the last number

## Set Theory
If a set S contains an element x, we write x ∈ S, and otherwise we write x ∉ S. 

For example, in the above set 4 ∈ X and 5 ∉ X . 

• The intersection A ∩ B consists of elements that are in both A and B. For example, if A = {1, 2, 5} and B = {2, 4}, then A ∩ B = {2}. 

• The union A ∪ B consists of elements that are in A or B or both. For example, if A = {3, 7} and B = {2, 3, 8}, then A ∪ B = {2, 3, 7, 8}. 

• The complement ¯A consists of elements that are not in A. The interpre- tation of a complement depends on the universal set, which contains all possible elements. For example, if A = {1, 2, 5, 7} and the universal set is {1, 2, . . . , 10}, then ¯A = {3, 4, 6, 8, 9, 10}. 

• The difference A \ B = A ∩ ¯B consists of elements that are in A but not in B. Note that B can contain elements that are not in A. For example, if A = {2, 3, 7, 8} and B = {3, 5, 8}, then A \ B = {2, 7}.