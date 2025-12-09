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


```C++
#include <bits/stdc++.h>
using namespace std;

void get_subsets(string &str, int k, const string &input) {
    if (k == input.size()) {
 // only print full-length subsets
            cout << str << '\n';
        return;
    }

    // include char k
    str.push_back(input[k]);
    get_subsets(str, k + 1, input);

    // exclude char k
    str.pop_back();
    get_subsets(str, k + 1, input);
}

int main() {
    string input;
    cin >> input;

    string subset;
    get_subsets(subset, 0, input);
}

```