Few sorting algorithm dominate: insertion sort is widely used: insertion sort for small data sets, while for large data sets. Merge sort and quick sort are often used.  

The simplest sorting concepts use repeated swapping of items in a list to sort it. 
# Selection Sort
Selection sort uses swapping and simple recursion; the idea is to select one item and then sort the rest. 

# Divide and Conquer
For large arrays a more efficient general recursive design technique is to split the problem into two half-sized problems. 
## Quick Sort
Quick sort takes an array segment, partitions it into two parts and recursively repeats the procedure on each of the parts until array segments contain less than 2 items

It has a best and average case of $O(n\log n)$. However $O(n^{2})$ is it's worst case, because partitioning may split $n$ items into unequal halves. This means that quick sort isn't always used when time is critical.
## Merge Sort
Merge sort is guaranteed to be $O(n\log n)$ and recursively combines two sorted array segments into a larger sorted one. Merge sort starts off by splitting the array into individual blocks recursively.  

# Partitioning a segment of an array
# Hoare's Algorithm
Move `lo` to the right until an element greater than or equal to the pivot is found, and move `hi` to the left until an element less than or equal to the pivot is found. 

If hi points to an element greater than or equal to the pivot and j points to an element less than or equal to the pivot, swap them.

Repeat the process, moving `lo` and `hi` toward each other until they meet or cross. If this happens then the partitioning is complete

Below is an example code Hoare's Algorithm
```C
int partition(int lo, int hi, item xs[]){
    while (true) {
        while(xs[lo] < p) lo++;
        while(xs[hi-1] > p) hi++;
        if(hi - lo <= 1) return hi;
            swap(lo, hi-1, xs);
            lo++;
            hi--;
    }
}

```

