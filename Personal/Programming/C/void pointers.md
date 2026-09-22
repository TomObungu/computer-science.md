https://www.youtube.com/watch?v=t7CUti_7d7c

For example in something like the `malloc` function. All the malloc function does is allocate memory off the heap and return a pointer to that memory. The type of the pointer doesn't matter. In this case `void *` is perfect. You can then convert type of the pointer within the code, hence the `sizeof` operator being used within a parameter. Below is a code example 
```C
struct *pPerson = (Person*) malloc(size(Person));
```
Since `malloc` returns a `void*`, you must type cast the `void*` to the `Person` data type. 

If you know the data type ahead of time when writing a function. Don't use `void*`. Should always try to include type information 