I had some conception of the solution. I was imagining finding difference between the larger of $a$ or $b$ and the smaller of $a$ and $b$ and then checking if the girl with the remaining button presses is greater than $c$ and then trying to return a result based on that.

I also deduced that if c is even then it will land back on a and if c is odd it will land back on b.

I was very nearly there but I had been demotivated by by original attempt which was brute force but ended up in TLE. Even then I think my brute force approach was still wrong:
```C++
#include <bits/stdc++.h>
using namespace std;

string solve(){
    int a, b, c;
    cin >> a >> b >> c;
    int turn = 0;
    while(1){
        turn %= 2;
        if(turn == 0){
            if(a > 0)
                a--;
            else if(c > 0)
                c--;
            else
                return "Second";
        } else{
            if(b > 0)
                b--;
            else if(c > 0)
                c--;
            else
                return "First";
        }
        turn++;
    }
}

int main(){
    int t;
    cin >> t;
    for(int tc = 0; tc < t; tc++)
        cout << solve() << '\n';
}
```

## Solution
Basically the first half of my initial conceptualisation can be transferred into wether $a>b$ or $b<a$. And if c is even then it will always land back on b and if c is odd then it will land back on b:

```C++
#include <bits/stdc++.h>
using namespace std;

string solve(){
    int a, b, c;
    cin >> a >> b >> c;
    if(c % 2 == 0)
        if(a > b)
            return "First";
        else 
            return "Second";
    else
        if(b > a)
            return "Second";
        else
            return "First";
}

int main(){
    int t;
    cin >> t;
    for(int tc = 0; tc < t; tc++)
        cout << solve() << '\n';
}
```