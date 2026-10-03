![[Pasted image 20250918172822.png]]
![[Pasted image 20250918173648.png]]

To solve this problem you need to ensure that (n(n+2))/2 % 2 == 0 (It's even). This means that sum of the two sets must equal to (n(n+1) / 2) / 2 = n(n+1)/4.  I

f this this is the case it can be proven that a solution is possible. The solution is reached by first having all the elements in set 1 and then continually moving numbers from set 1 to set 2 such that the number removed will make the calculation of n(n+1)/4 subtract the number removed, equal to another number in the set. This process is repeated until the target value is 0 or until the target number is zero
## Implementation
A standard method of implementation is to put all of the distinct integers of the permutation of n inside set 1. Have a variable named target that will indicate the target to be searched for within the set 1. Start of by setting the target to n(n+1)/4. Then subtract  the largest element within the set from target. If the result is in the set then reduce target to the result then add the element to set 2. Repeat for the next element in the set.

If the element is not in the set 

## Old solution
```C++
#include <iostream>

#include <vector>

#include <numeric>

  

using std::cout;

using std::cin;

using std::vector;

using std::iota;

  

signed main() {

unsigned n = 0;

cin >> n;

  

if (n == 1) {

cout << "NO"; exit(0);

}

  

unsigned sum_of_all_n = (n * ( n + 1 )) / 2;

  

bool division_possible = ((sum_of_all_n) % 2 == 0);

  

if(!division_possible) {

cout << "NO"; exit(0);

}

  

vector<unsigned> nums(n);

iota(nums.begin(), nums.end(), 1);

  

vector<unsigned> set_one{}, set_two{};

  

unsigned a = sum_of_all_n / 2, b = 0, r = 0;

r = a - nums[0];

if(r % 2 == 1) {

a = r; b += nums[0];

set_one.push_back(nums[0]);

}

for (unsigned i = 1; i < n; i++)

{

r = a - nums[i]; b += nums[i];

if (b + r == sum_of_all_n / 2) {

set_one.push_back(nums[r-1]);

break;

}

if(r % 2 == 1) {

a = r;

set_one.push_back(nums[i]);

}

else

set_two.push_back(nums[i]);

}

  

cout << "YES\n" << set_one.size() << '\n';

  

for (auto it = set_one.begin(); it != set_one.end(); ++it)

cout << *it << " ";

cout << "\n" << set_two.size() << '\n';

  

for (auto it = set_two.begin(); it != set_two.end(); ++it)

cout << *it << " ";

}
```