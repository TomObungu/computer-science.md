
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
> both numbers in the expres-sion a*a are of type int and the result is also of type int. Because of this, the variable b will contain a wrong result. 

[[[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen].pdf#page=16&selection=130,2,147,29|[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen], page 16]]

> an be solved by changing the type of a to long long or by changing the expression to (long long)a * a

[[[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen].pdf#page=16&selection=147,42,159,1|[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen], page 16]]

> Still, it is good to know that the g++ compiler also provides a 128-bit type __int128_t with a value range of −2127 . . . 2127 − 1 or about −1038 . . . 1038.

[[[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen].pdf#page=16&selection=164,11,196,1|[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen], page 16]]


## Modular Arithmetic
> Sometimes, the answer to a problem is a very large number but it is enough to output it ”modulo m”, i.e., the remainder when the answer is divided by m

[[[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen].pdf#page=16&selection=236,0,243,1|[CPH] [Competitive Programmer’s Handbook] [Antti Laaksonen], page 16]]

## 1.4
