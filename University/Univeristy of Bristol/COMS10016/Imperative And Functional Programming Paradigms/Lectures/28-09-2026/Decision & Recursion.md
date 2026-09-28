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

However our lecturerer advises to not use switch cases as it can make procedures unnecessarily big. Try to consider one line per case, maybe a function call - try to decompose your logic 