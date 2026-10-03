I managed to solve this problem first try (no wrong answer attempts) and even make it computationally identical to the editorial solution. This is W as it's second time I am starting to do this. This shows progress in my journey of CP and I am happy abt it:

```C++
#include <bits/stdc++.h>
using namespace std;

int solve() {
    int n, x;
    cin >> n >> x;
    vector<int> a(n);
    for(auto& e : a) cin >> e;
    sort(a.rbegin(), a.rend());
    int p1 = 0, p2 = 0, count = 1, min_elem, ans = 0;
    while(p2 < n && p1 < n){
        min_elem = min(a[p1],a[p2]);
        if(count * min_elem >= x){
            p1 = p2 + 1;
            p2 = p1;
            count = 1;
            ans++;
            continue;
        }
        p2++;
        count++;
    }
    return ans;
}

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t; cin >> t;
    while (t--) {
        cout << solve() << '\n';
    }
    return 0;
}
```