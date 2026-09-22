For this question I needed to recognise that net efficiency of the teams will be 0. 

Take an example of two teams scoring against each other. Team 1 scores 4 against team 2 and team 2 scores 1 against team. Team 1 's efficiency will be the numbers of goals scored subtract the number of goals conceded. In this case that is (4-1) = 3. Team 2's efficiency will be  (1 - 4) = -3 as they conceded 4 goals against team 1. 

From this example you can see that the efficiencies of the teams will be 3 and -3. You can see that the sum of all team efficiencies will be 0.

# Code
```cpp
#include <iostream>
#include <vector>

using std::cin;
using std::cout;

signed main(){
    int t = 0;
    cin >> t;
    while(t--){
        int n = 0;
        cin >> n;
        int sum = 0;
        for(int i = 0; i < n - 1; i++){
            int efficiency = 0;
            cin >> efficiency;
            sum += efficiency;
        }
        cout << -sum << '\n';
    }
}

```