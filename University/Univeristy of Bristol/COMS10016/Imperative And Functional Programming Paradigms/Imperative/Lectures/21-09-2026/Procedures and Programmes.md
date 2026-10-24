 An imperative language means it  uses sequences and commands to step-by-step define and change a computer's state to calculate a result.

A procedural language means that these sequences are structured in small, reusable chunks called procedures.

An example of an imperative and procedural language is C. Another type of imperative and procedural language is Ruby.  Learning C teaches you about computers; C is the lowest level language you are likely to use within university. 
# Procedures

Mathematical functions take arguments from well defined sets and return a result element from other well defined set. For example:
$$
f : Z \times Z \to Z
$$
In function notation:
$$
f(x,y) = x +y
$$
In C, the same above function would look like this:
```C
int f(int a, int b)
```

In C, functions consist of two parts, a signature such as `int(f(int x, int y)` and body surrounded by `{...}`

A function that only calculates the result using it's arguments is called a **pure** function. This means only the input parameters. 

## Consider the case of functions that don't return values

In A-level we were tought that blocks of code that encapsulate logic and take in put would be called sub-routines. 

Of these sub-routines, procedures are subroutines that do not return a value. However functions are sub-routines that do return a value. 

However my lecturer states that all procedures are functions. 

However most mathematicians may consider the function that does not return a value to not be a function. Mathematically you may consider a function that doesn't return a result as a function that maps the empty set to the empty set. 

Where as in the scope of a engineer, a function such a void function that doesn't return a result would still be considered a procedure. 

## Simple programs
A program must containt exactlty one procedure named `main`, which is started when the program is executed. 

```C
int main(void){
};
```



