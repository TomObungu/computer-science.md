## My approach
Firstly I would swap $a$ and $b$ if $a>b$
I was very close conceptually to solving this problem. I had realised that:
$$
b = 2^{k}a
$$
And that my intuition was towards trying to find a the value of $k$ that satisfies this condition.

I then came to conclusion to try and check if:
$$
\frac{b}{a} = 2^{k}
$$
This solution would be valid. I would find the value of $\frac{b}{a}$ and check if it was a power of $2$ by continuously dividing by $2$. Obviously if $b$ was not divisible by $a$, no solution exists.  

One I found $k$ I then would divide 3 and add one if there was remainder

Despite my solution being very close to the actual solution, it took me a few attempts to get my approach to work and I had only managed to tweak my approach to work by once looking at the editorial. 

## Solution

```C++
#include <bits/stdc++.h>

using namespace std;

typedef long long LL;

LL getR(LL a){
	while(a % 2 == 0)
		a /= 2;
	return a;
}

void solve(){
	LL a, b;
	scanf("%lld %lld", &a, &b);
	if(a > b)	swap(a, b);
	
	LL r = getR(a);
	if(getR(b) != r){
		puts("-1");
		return;
	}
	
	int ans = 0;
	b /= a;
	
	while(b >= 8)
		b /= 8, ++ans;
	if(b > 1)	++ans;
	printf("%d\n", ans);
}

int main(){
	int quest;
	scanf("%d", &quest);
	
	while(quest--)
		solve();
	return 0;
}
```