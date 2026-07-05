You can think of structs in C as a class with only data members and no methods. 

This is often done at the global scope outside any functions so that the struct is globally available. 

When using structs, you create a new type. 

# 8.1 & 8.2  

```C
struct car {
	char * name;
	float price; 
	int speed;
};

// declaring the type
struct car saturn = {"Saturn SL/2", 16000.99, 175};

// utilising the type

printf("Name: %s\n", saturn.name);
printf("Price: %f\n", saturn.price);
printf("Top Speed: %d km\n", saturn.speed);
```


It is possible to directly address the struct members:

```C
struct car saturn = {.speed=175, .name="Saturn SL/2"}
```


# 8.3 Passing structs in functions

To pass the struct into a function, you can either pass the struct by value or by reference. Passing in the struct directly will pass it by value. Passing a pointer to the struct will pass it by reference. 

Threre are two cases you'd want to pass a pointer to the struct
1. You need the function to make changes to the struct
2. It is cheaper to pass in a pointer to the stack than the struct itself

# 8.5 Copying and returning structs

Just assign one to the other and also return it from the function

```C
struct a,b;
b = a 


stuct c = myFunction();
```

The copies are not deep copies

Deep copies follows the pointers and copies the data they point to aswell. A shallow copy just copies the pointers. 

# 8.6