For this problem we are given a binary string of length $n$. We are asked to manipulate the string such that there are no sub-strings of length $m$ that are all consecutive $0$'s.

A single operation consists of selecting sub sub-string segments that are of length $k$ and flipping all the $0$'s to $1$.

The task is to find the minimum number of operations in which there are no sub-strings of length $m$ that are all consecutive $0$'s.

## My approach
My approach is very similar to the solution, that is I would find the first 0 in the sub-string. I would then iterate from the index of the 0 for $k$ times and check if it is a consecutive string of 0's. If there was a 1 as I was iterating for $k$ times, I would break. 

If I found the case where it was an consecutive string of $k$, then I would flip all the $0s$ to 1 and increment the counter for Timar used. 

My approach was almost the solution, It's just I faced some issues in implementation whilst writing my code or I had a minor logic error in the code
```C++
#include <iostream>
#include <string>
using std::string;
using std::cin;
using std::cout;
int main()
{
    unsigned t;
    cin>>t;
    for (unsigned i = 0; i < t; i++)
    {
       int n,m,k,timarUsed=0;
       cin>>n>>m>>k;
       string s;
       cin>>s;
       for (int i = 0; i < n; ++i)
        {
            if(s[i]=='0')
            {
                for (unsigned l = i; l < i+m; ++l)
                {
                    if(l <= n && s[l]=='1')
                        break;
                    else if (l==i+m-1 && s[l]=='0')
                    {
                        for (unsigned h = 0; h < k; ++h)
                        {
                            if(l+h <= n)
                                s[l+h]='1';
                        }
                        ++timarUsed;
                    }
                }
            }
        }
        cout<<timarUsed<<'\n';
    }
}
```

## Solution
The solution states:

Start from the leftmost spot and move rightwards.

 Whenever a consecutive segment of m weak spots (i.e., 0's) is found, apply Timar to a segment of length k- , starting from the last index of the weak segment.

 Repeat this process until no segment of consecutive weak spots remains.



