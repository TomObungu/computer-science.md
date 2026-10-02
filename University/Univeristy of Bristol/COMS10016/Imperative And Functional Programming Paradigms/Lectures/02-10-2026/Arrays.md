# Bad practices
## `break`
An advised practice is to not use the `break` statement within loops. 

## `return`
Furthermore it is also not advised to use `return` statements within the `main` loop due to ambigious return statemetns inside the loop and outside the loop. 

## `continue`
Ensure that counters are placed appropiatley when using the `continue` statement:
```C
int main(void){
    int i = 0;
    while( i < N){
        i++;
        if(i == STOP){
            continue;
        }
        printf("%d\n", i);
    }
    return 0;
}
```

## `do while()`
Another unadvised practice is using `do while()` loops. Remember that `do while()` loops run the iteration of code at least once before performing the iterations for `Nth` times. 

## `labels`
Another highly unadvised practice using statments such as `goto`
```C
int main(void){
    int i = 0;
loop:
    if(i >= N) goto done;
    printf("%d\n", i);
    i++;
goto loop;
done: 
    return 0;
}
```

