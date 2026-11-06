lcdFew sorting algorithms dominate: insertion sort is widely used: insertion sort for small data sets, while for large data sets. Merge sort and quick sort are often used.  

The simplest sorting concepts use repeated swapping of items in a list to sort it. 
# Selection Sort
Selection sort uses swapping and simple recursion; the idea is to select one item and then sort the rest. 
# Divide and Conquer
For large arrays a more efficient general recursive design technique is to split the problem into two half-sized problems. 
# Partitioning a segment of an array
The splitting of a list into two sublists as need for quick sort is called parti
## Hoare's Algorithm
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

## Quick Sort
Quick sort takes an array segment, partitions it into two parts and recursively repeats the procedure on each of the parts until array segments contain less than 2 items

```C
void qsort(int lo, int hi, item xs[hi]){
	if(hi -lo <= 1) return;
	int split = partition(lo, hi, xs);
	sort(lo, split, xs);
	sort(split, hi, xs);
}
```

It has a best and average case of $O(n\log n)$. However $O(n^{2})$ is it's worst case, because partitioning may split $n$ items into unequal halves. This means that quick sort isn't always used when time is critical.
## Merge Sort
Merge sort is guaranteed to be $O(n\log n)$ and recursively combines two sorted array segments into a larger sorted one. Merge sort starts off by splitting the array into individual blocks recursively.  

For the merge sort function below, it takes in a low, high and middle pointer. It then takes in the array to be sorted and an additional array to to store the sorted result.

The sorting algorithm works by starting off at the middle of the list and the recursively calling the `sort` function on each each sub segment of the list. Recursively, each sub segment is split in two until there is only 1 element. Once the sort function reaches the state of there sub segments being 1 element. 

```C
void sort(int lo, int hi, item xs[hi], item other[hi]){
	if(hi - lo <= 1) return;
	int mid = lo + (hi-lo)/2;
	sort(lo, mid, other, xs);
	sort(mid, hi, other, xs);
	merge(lo, mid, hi, xs, other);
}
```

![[Pasted image 20261106104746.png]]


Once the function has reached its state of the lists being independent element, the merge function works by comparing the single element arrays and sorting them. This merge function is called on each partitioned array. 
```C
void merge(int lo, int hi, item xs[hi], item other[hi]){
	int i = lo, j = mid;
	for (int k = lo; k < hi; k++){
		if ( i < mid && (j >= hi || xs[i] <= xs[j])){
			other[k] = xs[i++];
		} else {
			other[k] = xs[j++];
		}
	}
}
```

