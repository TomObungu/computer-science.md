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