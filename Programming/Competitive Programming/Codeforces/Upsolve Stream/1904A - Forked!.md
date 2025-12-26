I solved the problem. I just writing this out showcase the differences between my implementation and the editorial implementation. I might need this in a future question.

## My solution

```C++
#include <bits/stdc++.h>
using namespace std;

#define fastio ios_base::sync_with_stdio(false); cin.tie(0);
using ll = long long;

int solve() {
    ll a, b;
    cin >> a >> b;
    ll xk, yk;
    cin >> xk >> yk;
    ll xq, yq;
    cin >> xq >> yq;
    vector<pair<ll,ll>> mvs = {
        {a,b},{a,-b},{b,-a},{-b,-a}, 
            {-a,-b},{-a,b},{-b,a},{b,a} 
    };
    set<pair<ll,ll>> kng_atk, qn_atk;
    for(auto [dx, dy] : mvs){
        kng_atk.insert({xk + dx, yk + dy});
        qn_atk.insert({xq + dx, yq + dy});
    }
    int ans = 0;
    for(auto &pos : kng_atk){
        if(qn_atk.count(pos))
            ans++;
    }
    return ans;
}

int main() {
    fastio

    int t;
    cin >> t;
    while (t--) {
        cout << solve() << '\n';
    }
}

```
## Editorial
```C++
#include <bits/stdc++.h>
using namespace std;
 
int dx[4] = {-1, 1, -1, 1}, dy[4] = {-1, -1, 1, 1};
 
int main(){
    int t; cin >> t;
    for(int i = 0; i < t; i++){
        int a, b; cin >> a >> b;
        int x1, y1, x2, y2; cin >> x1 >> y1 >> x2 >> y2;
        set<pair<int, int>> st1, st2;
        for(int j = 0; j < 4; j++){
            st1.insert({x1+dx[j]*a, y1+dy[j]*b});
            st2.insert({x2+dx[j]*a, y2+dy[j]*b});
            st1.insert({x1+dx[j]*b, y1+dy[j]*a});
            st2.insert({x2+dx[j]*b, y2+dy[j]*a});
        }
        int ans = 0;
        for(auto x : st1)
            if(st2.find(x) != st2.end())
                ans++;
        cout << ans << '\n';
    }
} 
```