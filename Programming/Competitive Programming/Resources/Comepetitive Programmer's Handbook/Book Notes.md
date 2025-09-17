
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

If each element of A also belongs to S, we say that A is a subset of S, denoted by A ⊂ S. 

 **set S always has 2|S| subsets,** including the empty set. 
 
 For example, the subsets of the set {2, 4, 7} are

The $\phi$ symbol denotes an empty set

$\phi$ {2}, {4}, {7}, {2, 4}, {2, 7}, {4, 7} and {2, 4, 7}.

# Logic
![[Pasted image 20250917203518.png]]

A quantifier connects a logical expression to the elements of a set. The most important quantifiers are ∀ (for all) and ∃ (there is). For example,

∀x(∃y(y < x))

This means for all x there is an element y such that y < x. This is true for all integers but false in the set of natural numbers

![[Pasted image 20250917203809.png]]

## Floor and ciel
![[Pasted image 20250917203853.png]]
## Closed form fomula for calculating nth fibbonacci number

$f(n) =$
$$
\frac{(1+\sqrt{ 5 })^{n}-(1-\sqrt{ 5 })^{n}}{2^{n}\sqrt{ 5 }}
$$

## Logarithms
![[Pasted image 20250917204112.png]]


## 1.6 

### IOI
> The International Olympiad in Informatics (IOI) is an annual programming contest for secondary school students. Each country is allowed to send a team of four students to the contest. There are usually about 300 participants from 80 countries

[[[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen].pdf#page=25&selection=65,0,68,9|[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen], page 25]]

The IOI consists of two five-hour long contests. In both contests, the partic- ipants are asked to solve three algorithm tasks of various difficulty. The tasks are divided into subtasks, each of which has an assigned score. Even if the contestants are divided into teams, they compete as individuals. The IOI syllabus [ 41] regulates the topics that may appear in IOI tasks. Almost all the topics in the IOI syllabus are covered by this book. Participants for the IOI are selected through national contests. Before the IOI, many regional contests are organized, such as the Baltic Olympiad in Informatics (BOI), the Central European Olympiad in Informatics (CEOI) and the Asia-Pacific Informatics Olympiad (APIO). Some countries organize online practice contests for future IOI participants, such as the Croatian Open Competition in Informatics [11] and the USA Comput- ing Olympiad [ 68]. In addition, a large collection of problems from Polish contests is available online [60].

### ICPC
The International Collegiate Programming Contest (ICPC) is an annual program- ming contest for university students. Each team in the contest consists of three students, and unlike in the IOI, the students work together; there is only one computer available for each team. The ICPC consists of several stages, and finally the best teams are invited to the World Finals. While there are tens of thousands of participants in the contest, there are only a small number2 of final slots available, so even advancing to the finals is a great achievement in some regions. In each ICPC contest, the teams have five hours of time to solve about ten algorithm problems. A solution to a problem is accepted only if it solves all test cases efficiently. During the contest, competitors may view the results of other

## Books
![[Pasted image 20250917204338.png]]

## 2.3
![[Pasted image 20250917204621.png]]For example, if the input size is n = 105, it is probably expected that the time complexity of the algorithm is O(n) or O(n log n). This information makes it easier to design the algorithm, because it rules out approaches that would yield an algorithm with a worse time complexity. Still, it is important to remember that a time complexity is only an estimate of efficiency, because it hides the constant factors. For example, an algorithm that runs in O(n) time may perform n/2 or 5n operations. This has an important effect on the actual running time of the algorithm

# 2.4 Maximum subarray sum
How could we the find maximum subarray of a given array n. Interesting problem when the integers given can be negative

### Method 1
Simply go through all possible subarrays and calculate the sum of the values and maintain the maximum sum:

```C++
int best = 0;
for (int a = 0; a < n; a++) {
	for (int b = a; b < n; b++) {
int sum = 0;
for (int k = a; k <= b; k++) {
sum += array[k];
}
best = max(best,sum);
}
}
cout << best << "\n"
```