Passing by value takes a copy of the value and all modifications to the value in the function, are modifications to the copy only. 

Function prototypes can notify the compiler in advance that you'll be using a function of a certain type.  These prototypes can go inside a `.h` file. 

```C
int foo(void);

int main(void){
	int i;
	// can call foo() here 
	
	i = foo()
	
	printf("%d\n", i); // return 1337
}


int foo(void){
	return 1337;
}
```


