If you are given $N$ numbers, check if there is a subset of them such that sum of that subset is equal to some target value $S$. This is for the case when you cannot take each element more than once.
# Method 1 : using bit masks
https://youtu.be/xXKL9YBWgCY?si=l1zlpgPimmhsEEGi&t=556

This method is effective for when $N\leq 20$. 

This algorithm works by using a bit mask of $x$ where $1\leq  x \leq N$. 