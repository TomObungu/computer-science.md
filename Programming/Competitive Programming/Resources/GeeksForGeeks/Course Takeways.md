
# Reverse an array
Overall it is better to use inbuilt sorting functions provided by the language's standard library rather than implementing your own. 

In C++, std::sort allows passing in a callback function for sorting conditions.

```C++
std::sort(mMyClassVector.begin(), mMyClassVector.end(), [](const MyClass &a, const MyClass &b)
{ 
    return a.mProperty > b.mProperty; 
});
```


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

## Sum Of Digits in a number
The best way to work out the sum of digits in a given number
```C++
    string s = to_string(n);
    vector<int> digits;
    
    for (char c : s) 
	    digits.push_back(c - '0');
	for (auto it = vec.begin(); it != vec.end(); ++it) 
		cout << it << " \n"[it != vec.end()]
```

## Check if a string a palindrome
```
string s {};
cin >> s;

```