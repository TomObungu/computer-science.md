```C++
#include <bits/stdc++.h>
using namespace::std;

// Generate subsets of a given array n


void print_vec_2d(vector<vector<int>>& arr){
    for(int i = 0; i < (int) arr.size(); i++){
        cout << '{';
        for(int j = 0; j < (int) arr[i].size(); j++) {            
            cout << arr[i][j];
            if (j != arr[i].size() - 1) cout << ", ";
        }
        cout << '}' << '\n';
    }

}

void get_subsets(int i, vector<int>& arr, 
    vector<vector<int>>& res, vector<int>& subset){
        if( i == arr.size()){
            res.push_back(subset);
            return;
        }

        subset.push_back(arr[i]);
        get_subsets(i+1, arr, res ,subset);
        subset.pop_back();
        get_subsets(i+1, arr, res ,subset);
}
// generate subsets using recursion
vector<vector<int>> gen_subsets(vector<int>& arr)
{
    vector<vector<int>> res;
    vector<int> subset;
    get_subsets(0, arr, res, subset);
    return res;
}

int main(){
    vector<int> arr{1, 2 ,3};
    vector<vector<int>> subsets = gen_subsets(arr);
    print_vec_2d(subsets);
    return 0;
}
```
