In programming languages such as C there exists things known as forward declerations. This means that procedures are allowed to be declared procedures before defining it. 

This is known as prototyping and allows us to call procedures before the program point at which they are defined. 

It resolves the problem of otherwise impossible mutual function calls and relaxes procedural ordering constraints. 

```C
int grade(int mark); // declaration of signature only
...
int main(void) { ...
grade(mark)); ...
}
...
int grade(int mark) { ... } // full definition with body
```

It is possible to use forward declarations for useage of header files for multi-file projects. 

# Shadowing
The procedure identifier has global scope, whilst the variable grade has a local scope limited to this procedure only. In such situations the identifier declared last takes precedence and all other identifiers of the same name are temporarily not accessible or shadowed.  We are usually not allowed to declare the same identifier name twice in exactly the same scope. 

This means that the local variable grade within the innermost function will take priority. 

```C
int grade(int mark); // declaration of signature only
...
int main(void) { ...
grade(mark)); ...
}
...
int grade(int mark) { ... } // full definition with body
```

This is called shadowing. 

# Switch Statements
A switch statement allows executing different statemets baed on a testing integer expression. Below is the syntax for switch statements:

```C
switch (INT_EXP) {
	case CONST_EXP1:
	{
		STATEMENTS1; 
		break;
	}
		case CONST_EXP2:
	{
		STATEMENTS1; 
		break;
	}
	default:
	{
		STATEMENTS;
	}
}
```

However our lecturerer advises to not use switch cases as it can make procedures unnecessarily big. Try to consider one line per case, maybe a function call - try to decompose your logic.

One of the things that seperates the `default` statement and `else` is that the statement only depends on if a case was not broken before. If a case is broken before the `default` keyword is reached, then the `default` statement is never called.

# Recursion

# Self-Calling Produres
I like to visualise recursive functions using reccurence relations as mentioned within the exercises.

Consider this case:
```C
int sum(int n){
    if( n == 1) return 1;
    else return n + sum(n-1);
}
```

For example take the concept of triangle numbers. Mathematically triangle numbers can be expressed using the the recurrenece relation of:
$$
\begin{gather*}
T(n_{i}) = n \\ \\
T(n_{i+i}) = n + (n+1)
\end{gather*}
$$
For example consider a function for the recursive form to get the $nth$ triangle number. In this case we can define the base case of $T(n)$ within this section of the code:
```C
if (n == 1)
```
For the following $n+1th$ recurrence relation, the secondary base cases can be represented as this:
```C
else return n + sum(n-1);
```

In recursion, functions are called in order and placed on the call stack in reverse order. Each function is then called from reverse order called with its instance and variables for that function:

![[Pasted image 20260928104045.png]]

# Call Stack
A processor has access to a call stack, containing stack frames. Each function  call generates an instance of local variables written on, one for each function call which is in progress. 

![[Pasted image 20260928104152.png]]

The call stack is efficient as as the functionality to return and call instances is built into the frame. 

# Global Variables
In C if you have programs which require sharing of multiple variables between files then global concurrency would be required. In 