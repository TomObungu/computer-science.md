You can think of structs in C as a class with only data members and no methods. 

This is often done at the global scope outside any functions so that the struct is globally available. 

When using structs, you create a new type. 

```C
struct car {
	char * name;
	float price; 
	int speed;
};

// declaring the type
struct car saturn
```

