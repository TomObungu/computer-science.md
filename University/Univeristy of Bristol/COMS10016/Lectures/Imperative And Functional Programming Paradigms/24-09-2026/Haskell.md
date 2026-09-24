Within Haskell, the lamba function $\lambda$ is synonmous with a function declaration within imperative langauges. However lambda functions are not named. In the imperative counterparts, functions must have named declarations. In some imperative languages such as C and JavasScript, lambda functions are actually implemented to be functions without names.

1. Evaluating varaibles, substitute the varibles with its definition:

```Haskell
{-
	x = 10 
-}
```


2. Evaluating function application: Declare the input variable to be equal to the provided  argument and evaluate the body:
```Haskell
(\x -> x + 5) 5]
-- ==> {- x = 5 -} x + x
```

When declaring named functions, you can assign lambda functions to variables using the $=$:
```Haskell
f = \y -> y * 10
```