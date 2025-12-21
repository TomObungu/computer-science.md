I solved this problem, however I reading to get some takeaways for implementation:

## My implementation
```C++
#include <bits/stdc++.h>
using namespace std;

typedef long long ll;

void print_vec(vector<ll> arr){
    int n = arr.size();
    for(int i = 0; i < n - 1; i++)
        cout << arr[i] << " ";
    cout << arr[n - 1] << '\n';
}

int main()
{
    int t;
    cin >> t;
    for(int tc = 0; tc < t; tc++){
        int n;
        cin >> n;
        ll temp = 0;
        cin >> temp;
        ll min_elem = temp;
        vector<ll> a(n), b{}, c{};
        a[0] = temp;
        for(int i = 1; i < n; i++){
            ll x;
            cin >> x;
            min_elem = min(x, min_elem);
            a[i] = x;
        }
        set<ll> as(a.begin(),a.end());
        if( as.size() == 1){
            cout << -1 << '\n'; continue;
        }
        for(auto& elem : a){
            if(elem == min_elem)
                b.push_back(elem);
            else
                c.push_back(elem);
        }
        cout << b.size() << " " << c.size() << '\n';
        print_vec(b); print_vec(c);
    }
}
```

## Solution's Implementation
```C++
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
 
void solve() {
	int n = 0; cin >> n; 
	vector<int> inp; inp.assign(n, 0);
	for (auto& x : inp) cin >> x;
	sort(inp.begin(), inp.end());
	if (inp.back() == inp[0]) {
		cout << "-1\n";
		return;
	}
	else {
		int it = 0;
		while (inp[it] == inp[0]) it++;
		cout << it << " " << n - it << "\n";
		for (int j = 0; j < it; ++j) cout << inp[j] << " ";
		for (int j = it; j < n; ++j) cout << inp[j] << " ";
	}
}
 
int main() {
	int t = 0; cin >> t;
	while (t--) solve();
	return 0;
}
```

## Takeaways:
Method to check if all elements in array are all the same. My method has the same time complexity of $O(n)$ however it also has space complexity of $O(n)$ and mine also has additional overhead based on taking input and then iterating again:
```C++
sort(inp.begin(), inp.end());
	if (inp.back() == inp[0]) {
		cout << "-1\n";
```

As well as that, the minimum element will always be at the beginning of the array. As well as that counting the iterations of how much it appears also accounts for 
```C++
		int it = 0;
		while (inp[it] == inp[0]) it++;
```
So I do no