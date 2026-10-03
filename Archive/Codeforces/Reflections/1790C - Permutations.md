Another progress check. Managed to solve my first 1000 rated problem first try without any errors. The problem really helped me practice my implementation. Was quiet surprised when it worked as it did on paper:

For future me:
1. I took in the input of each sequence e.g. 4 2 1
	1. As I was taking in the input, I summed up the input and compared them with total sum until N. I then found the difference between them. This gave the missing integer in the sequences
2. I then generated each possible sequence e.g. For 4 2 1 -> 3 4 2 1, 4 3 2 1, 4 2 3 1 etc..
3. For each sequence that is newly generated:
	1. I would simulate the question by starting from i = 0 and then remove 
```C++
#include <bits/stdc++.h>
using namespace std;

template <typename T>
ostream& operator<<(ostream& os, const vector<T>& vec) {
    bool first = true;
    for (const auto& elem : vec) {
        if (!first) os << ' ';
        os << elem;
        first = false;
    }
    return os;
}

void solve() {
    int n;
    cin >> n;{}
    map<vector<int>,int> seqs{};
    for(int i = 0; i < n; i++){
        vector<int> seq(n-1);
        int sum = 0, x, tot = n*(n+1) / 2;
        for(auto& e : seq)
            cin >> x, e = x, sum += x;
            seqs[seq] = tot - sum;
    }
    auto it = seqs.begin();
    while(it!= seqs.end()){
        vector<int> curr_seq(it->first); int missing = it->second;
        for(int i = 0; i < n; i++){
            vector<int> temp(curr_seq);
            temp.insert(temp.begin() + i, missing);
            bool valid = true;
            for(int j = 0; j < n; j++){ 
                vector<int> check(temp);
                check.erase(check.begin() + j);
                valid = seqs.count(check);
                if(!valid)
                    break;
            }
            if(!valid)
                continue;
            else
                cout << temp << '\n'; return;
        }
    }    
}

int main(){
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t; cin >> t;
    while (t--) {
        solve();
    }
    return 0;
}
```
