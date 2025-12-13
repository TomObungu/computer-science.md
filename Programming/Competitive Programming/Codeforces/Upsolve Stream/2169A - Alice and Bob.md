# My approach
My mistake was was simply taking the mathematical statements at face 
value and trying to brute force a value of $b$. 

I looped for every possible value of $b$ up to supposedly $2\times 10^{9}$ , took the absolute difference between element $v_{i}$ and compared if it was less than the absolute difference for the current value of $a$.  

For each time this was the case, I would increment a point variable to signify the amount of points bob got.  

I would then store the point variable using a temporary variable and compare if it was greater than the previous value of the point variable. If it was, I would store that as the result of value of $b$. 

 Although the approach worked, it yielded $O(n^{2})$ time complexity. Since, n was large of up to $2 \times 10 ^{9}$ then this approach guaranteed a time limit exceeded:
```C++
int solve() {
    ll n = 0, a = 0;
    cin >> n >> a;

    vector<ll> v(n);
    for(auto& i : v) cin >> i;

    ll b = 0;
    
    ll p = 0, tp = 0;
    for(ll i = 0; i < 300000; i++){
        if( tp > p) b = i, p = tp;
        tp = 0;
        for(auto& v_i : v)
            if(abs(v_i - a) > abs(v_i - i))
                tp++;
    }
    return b;
}
```

## Solution
For every integer $v_{i}$ in the marbles bag, $v_{i}<a$, $b=a-1$ will always be closer to $v_{i}$ than $a$. 

Thus using $b=a-1$, the number of points Bob gets will be equal to the the number of marbles having $v_{i} <a$ .

Using any $b < a - 1$ results in the answer not becoming better. 

And for any $v_{i}> a$, $b>a$ will always be closer to $v_{i}$ than $a$  

Thus using  using $b=a+1$, the number of points Bob gets will be equal to the number of marbles having $v_{i}>a$. 

So it is is enough to check only $b=a-1$ and $b=a+1$ and compare the points received for both scenarios. Return the value of $b$ yielding the largest points. 