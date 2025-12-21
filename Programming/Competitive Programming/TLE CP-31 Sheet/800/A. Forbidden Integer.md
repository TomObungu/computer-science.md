https://codeforces.com/problemset/problem/1845/A
The problem is about considering the least amount of cases possible. I propose the following options.

If x≠1
, then you can always print n

ones. So the answer is YES.

If k=1

, then no integer is available, so the answer is NO.

If k=2
, then only 2 is available, so you can only collect even n

. So if it's odd, the answer is NO.

Otherwise, you can always collect n
with the following construction: if n is even then take 2, otherwise take 3. Then take ⌊n2⌋−1 twos. You can see that an even n only uses twos, so it fits the previous check. If it's odd, then k is at least 3, so 3

is allowed to take.

Overall complexity: O(n)
per testcase.

```c++
void solve() {
    int n, k, x;
    cin >> n >> k >> x;
    if(x != 1){
        cout << "YES\n" << n << '\n';
        for(int i = 1; i <= n; i++) cout << 1 << " \n"[(i == n)];
        return;
    } else if(k == 1 ||  k == 2 && n & 1){
        cout << "NO" << '\n'; return;
    } else  {
        cout << "YES\n" << n / 2 << '\n';
        cout << (n & 1 ? 3 : 2) << " ";
        for(int i = 1; i <= n / 2 - 1; i++) cout << 2 << " \n"[(i == n / 2 - 1)];
        return;
    }
}

```