In about 1 second. It possible to perform 10^8 operations. If there are 100 test cases this means the average operations per test cases is limited to 

10^8 / 10 ^ 2 = 10 ^ 6 (operations/per test case)

For n approximately  100 solutions
 
The maximum time complexity is 100^3 = 10^6  operations. Thus for n = 100, with a time limit of 1 second. The maximum O() (time complexity) an algorithm can have is O(n^3). Thus, for any solution with time complexity O(n^2), O(nlogn), O(n), O(logn), O(1) is viable. 

# Simplify a question
![[Pasted image 20250918225907.png]]

# Solution
For this question you must recognise that if there are 3 distinct integers in the array then it is impossible to have such an array:
![[Pasted image 20251011192952.png]]
As well as that, every odd position must have the same integer and every even position must also have the same integer
![[Pasted image 20251011192936.png]]
The code approach can be reused for future scenarios, especially this snippet of code that pertains the condition for odd number input size:
```C++
int n = 0;
cin >> n;
vi nums(n);
for(size_t i = 0; i < n; i++)
cin >> nums[i];
map<int,int> freq_map;
for (size_t i = 0; i < n; i++){
freq_map[nums[i]]++;
}
if(freq_map.size() >= 3)
return "No";
int freq_1 = freq_map.begin()->second;
int freq_2 = freq_map.begin()->second;
if(freq_1 = freq_2)
return "Yes";
else if(n % 2 == 1 && abs(freq_1 - freq_2) == 1)
return "Yes";
else
return "No"
```