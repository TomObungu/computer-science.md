Compare a known length of matching patterns in a vector:  

```C++
	if(cells[i-1] == '.' && cells[i] == '.' && cells[i+1] == '.')`
```
---
Find an element in an vector or a string:
```C++
x.find(s)
```
___
Check if a hash table contains a certain key:
```C++
distinctNums.count(product)
```
Will return 0 or 1 - Can be used for Boolean comparisons

---
Check if iterable is is sorted in ascending order
```C++
is_sorted(perm.begin(), perm.end())
```

Check if iterable is sorted in descending order
```C++
`is_sorted(perm.begin(), perm.end(), greater<int>)
```
---
Overloaded  function to output a vector using cout
```C++
template <typename T>std::ostream& operator<<(std::ostream& os, const std::vector<T>& vec) {    
	for (auto elem = vec.begin(); it != vec.end(); ++it)        
		os << elem << " \n"[it != vec.end()]   
	return os;
}
```
---
Output a vector in order or in reverse order:
```C++
for (auto it = vec.rbegin(); it != vec.rend(); ++it)    
	cout << it << " \n"[it + 1 == vec.rend()]
```

```C++
for (auto it = vec.begin(); it != vec.end(); ++it)    
	cout << it << " \n"[it + 1 == vec.end()]
```

Check if an element is equal to specific address in range loop:
```C++
&elem != vec.back()
```

---
Use min_iterator to find the smallest element in an iterable:
```C++
auto min_it = min_element(vec.begin(), vec.end());
```
To print the iterator deference it using \* :
```C++
cout << *min_element(vec.begin(),vec.end())
```

Find the index of an element in an iterable:
```C++
distance(vec.begin(), min_it)
```
Can add a custom callback function to min_element to have conditions. In this case the condition is to check if the magnitude of the the in the current element smallest element **a** is less than the magnitude of another smallest element **b** within the given range of the iterator. Tell iterator to consider the element with the smaller absolute value
```C++
auto min_it = min_element(vec.begin(), vec.end(), [](int a, int b)
{
	return abs(a) < abs(b)
};
```
Using max_element will do the same except it will return the element with the largest absolute value:
```C++
result = max_element(v.begin(), v.end(), 
	[](int a, int b)    {        
		return std::abs(a) < std::abs(b);    
	});
```

---
 
  Lambda functions can capture variables
 
Can be used as callback function in functions such as `sort()` or `for_each()`
Has follow parts:
`[capture-list](parameters) -> return-type { function-body }`

1. `[]` How the Lamba function can access its surrounding variables in its surrounding scope. `[&]` is default capture mode and tells the lambda function to use its variables it its scope by reference. 
2. `[=]` Use variables by value (copy the variables)
3.  `[my_varible]` to capture an external variable to use within the function by value
4. `[&my_varible]` to capture an external variable to use within the function by reference
5. `[=, &my_varible]` to capture most external variable by copy except for `my varible` by reference
   
Use lambda to find a value closest to a specific value:
``` C++
 std::vector<int> v = {10, 25, 42, 50, 63};
    int target = 45;

    // We capture 'target' by value so the lambda can use it.
    auto closest = std::min_element(v.begin(), v.end(), 
        [target](int a, int b) {
            return std::abs(a - target) < std::abs(b - target);
        }
    );
    
    // Return 42
```

Use lambda to sum of values in array:
```C++
std::vector<int> numbers = {1, 2, 3, 4, 5};
    long long sum = 0;

    // Capture 'sum' by reference to accumulate the total
    std::for_each(numbers.begin(), numbers.end(), 
        [&sum](int n) {
            sum += n;
        });
```

Can use lambda and for each for any desire logic however make sure there already isn't an implementation of it as a function

Can use lambda function to implement custom sort function for custom data structures based on criteria
```C++
std::vector<Employee> employees = {
        {"Alice", 30},
        {"Bob", 25},
        {"Charlie", 35}
    };

    // Sort employees by age using a lambda
    std::sort(employees.begin(), employees.end(),
        [](const Employee& a, const Employee& b) {
            return a.age < b.age;
        });
```

---
Return each digit from an number:
```C++
int n = 12345;
    std::string s = std::to_string(n);
    std::vector<int> digits;
    
    for (char c : s)vdigits.push_back(c - '0');
	for (auto it = vec.begin(); it != vec.end(); ++it) cout << it << " \n"[it != vec.end()]
```
---

Generate a pattern sequence array:
```C++
	const int n;
    cin >> n;
    std::vector<int> arr(n);
    const std::array<int, 3> pattern = {1, 2, 3};
    int i = 0;
    std::generate(arr.begin(), arr.end(), [&]() {
        return pattern[i++ % pattern.size()];
    });
    
    ```


--- 
Generate an arithmetic progression using iota and transform
```C++
int main() {
    const int size = 10;
    std::vector<int> arr(size);
    const int start = 2;
    const int step = 2;

    // Step 1: Fill the vector with an index-like sequence (0, 1, 2, ...)
    std::iota(arr.begin(), arr.end(), 0);

    // Step 2: Transform each index into the correct arithmetic progression value
    std::transform(arr.begin(), arr.end(), arr.begin(),
        [start, step](int i) {
            return start + i * step;
        });
```
---
Using genrerate to from a vector of specific properties:
```C++
	const int size = 10;
    std::vector<int> arr(size);
    int current_value = 2;
    const int step = 2;
    
    // Capture `current_value` by reference so the lambda can modify it.
    std::generate(arr.begin(), arr.end(), [&]() {
        const int result = current_value;
        current_value += step;
        return result;
    });
```
---
Dynamically take input with input conditions that can have side effects on the container
```C++
vector a;        
for (int i = 0; i < n; ++i) {            
	int x;            
	cin >> x;            
	if (i && a.back() > x)  // Some arbritary condition
	{                
		a.push_back(1);            
	}            
	a.push_back(x);        
	}
```
--- 
General way to alternate between two numbers:
```C++
            while(valid_nth_num  < n)

            {

                if(counter % 2 != 0)

                {

                    valid_nth_num += 1;
                 ...
                 
              counter++
```