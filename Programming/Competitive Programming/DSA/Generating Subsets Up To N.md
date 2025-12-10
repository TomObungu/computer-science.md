```
#include <bits/stdc++.h>
using namespace::std;

/*  
    Generate subsets of n
    E.g n = 3
    Subsets of n will be:
    1
    2
    3
    12
    etc...
*/ 

bool print_vec(vector<int> arr){
    if(arr.empty())
        return 0;
    cout << '{';
    for(int i = 0; i < (int) arr.size() - 1; i++)
        cout << arr[i] << ", ";
    cout <<  arr.back() << '}' << '\n';
    return 1;
}

// generate subsets using recursion
int gen_subsets(vector<int> arr, int n, int k) // k = current index of subset
{
    if( k > n){
        print_vec(arr);
        return 0; 
    } 

    // include 
    arr.push_back(k);
    gen_subsets(arr, n, k + 1);
    // exclude
    arr.pop_back();
    gen_subsets(arr, n, k + 1);
    return 0;
}

int main(){
    vector<int> arr{};
    gen_subsets(arr, 3, 1); // starting from 1 e.g will print out {1}, {1,2} etc...
    return 0;
}
```