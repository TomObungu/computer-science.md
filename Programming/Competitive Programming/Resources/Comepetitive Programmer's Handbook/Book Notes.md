

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