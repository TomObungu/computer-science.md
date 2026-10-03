Know for future with implementation. This is what I was doing:
```C++
int solve() {
    int n = 0;
    cin >> n;
    multiset<int> a{};
    for(int i = 0; i < n; i++){
        int x = 0;
        cin >> x;
        a.emplace(x);
    }
    while(a.size() != 1){
        auto it = a.begin();
        ll floor_avg = (*it + *(++it)) / 2;
        a.erase(it); a.erase(++it);
        a.emplace(floor_avg);
    }
    return *a.begin();
}
```

The safe way to implement it and for future uses:
```C++
int solve() {
    int n;
    cin >> n;

    multiset<int> a;
    for (int i = 0; i < n; i++) {
        int x;
        cin >> x;
        a.emplace(x);
    }

    while (a.size() > 1) {
        auto it1 = a.begin();
        auto it2 = next(it1);   // safe second iterator

        long long floor_avg = (*it1 + *it2) / 2;

        a.erase(it1);
        a.erase(it2);
        a.emplace(floor_avg);
    }

    return *a.begin();
}
```
However to try and get random access using the set data structure degenerates the time complexity to $O(n^{2})$ as n gets larger when using sets:
```C++
auto it1 = a.begin();
std::advance(it1, i);

auto it2 = a.begin();
std::advance(it2, j);
```



My logic could have also been simulated using a priority queue:
```C++
priority_queue<int, vector<int>, greater<int>> pq;

while (pq.size() > 1) {
    int x = pq.top(); pq.pop();
    int y = pq.top(); pq.pop();
    pq.push((x + y) / 2);
}
```