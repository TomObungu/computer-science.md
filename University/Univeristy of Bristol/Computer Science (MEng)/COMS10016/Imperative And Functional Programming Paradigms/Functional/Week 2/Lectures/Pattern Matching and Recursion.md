# Branching 
Branching is a programming language's way of making descion based on input. All conditional/branching in Haskell is ultimately done with pattern matching. It is possible to pattern match in Haskell using case expressions, if else clauses and gaurd clauses. 

The function below is a function `foo` which takes in input `x` and if `x` is it returns "bish" or  if `x` is `2` it returns "bash". 
```Haskell
foo x = case x of
          1 -> "bish"
          2 -> "bash"
          _ -> "bosh" 
```
Patterns are tied in order, thus it will return the first successful case of `x`. In this case `foo'` will return "bish" first only:
```Haskell
foo' x = case x of
           1 -> "bish"
           2 -> "bash"
           1 -> "bing"
           _ -> "bosh"
```
Furthermore, Haskell is  whitespace sensitive language, thus, indentation is important. The following code will give a syntax error:
```Haskell
foo'' x = case x of
             1 -> "bish"
           2 -> "bash"
               _ -> "bosh"
```
Case expressions are similar to switch cases statements in C but they are not limited to integers only.

## Partial functions
A partial function only covers all possible patterns i.e the pattern matching is incomplete. Compiling the function below with throw a compilation error. Enabling `-Wincomplete-patterns` in the `ghc` compiler options will always throw an error for incomplete functions
```Haskell
badPat x = case x of
1 -> "one!"
2 -> "two!"
```
In general you want to make sure you write complete functions which include a default pattern. A default pattern includes something like `_` to catch any cases that have not been listed:
```Haskell
numToWord n = case n of
  1 -> "One"
  2 -> "Two"
  3 -> "Three"
  4 -> "Four"
  5 -> "Five"
  _ -> "I can only count to five"
```

# Syntax Sugar
It possible to write the above pattern matching expressions directly using `=` operators
```Haskell
fooSugar 1 = "bish"
fooSugar 2 = "bash"
fooSugar _ = "bosh"
```
## Booleans
When dealing with the conditionals or`Bool` type directly, it is possible to use `if/else` chains with the `=` operator
```Haskell
egIfSugar x = if x > 10
              then "Bigger than 10"
              else "10 or less"
```
### Guard clauses 
Guard clauses using the `|` operator allow the same functionality 
```Haskell
egGuardSugar x
  | x < 0     = "Negative"
  | x <= 9    = "Single-digit"
  | otherwise = "Multi-digit"
```
Below would what the gaurd clause would look like using only `if/else` chains
```Haskell
egGuardDesugar x
  = if x < 0
    then "Negative"
    else if x <= 9
         then "Single-digit"
         else "Multi-digit"
```
 And below is what it would it look like fully free of syntax sugar as a full lambda and case expression:
 ```Haskell
 egGuardDesugarest = \x ->
  case x < 0 of
    True -> "Negative"
    False ->
      case x <= 9 of
        True  -> "Single-digit"
        False -> "Multi-digit"
 ```

# Let and Where - Local Variables
It is possible to introduce an number of local variables using either `let`or `where` when dealing pattern matching. The syntax for `let...in...` is like below
```Haskell
let variable = expression 
in statementUsingExpression
```
For example the code below allows `result` to defined as an expression and then evaluted in the `in` clause
```Haskell
let myFunc =
	let result = x * 2
	in result + 1
```
The above function doubles `x` in `result` and then returns the expression plus 1

It possible to also return a defined `result` and the variable are defined after regardless of order
```Haskell
whereEg x = result
  where
    xCubed = x * x * x
    result = xCubed + xSquared
    xSquared = x * x
```

# C-syntax
It is possible to write cases statement like this with semi-colons
```Haskell
foo''' x = case x of {
             1 -> "bish";
             2 -> "bash";
             _ -> "bosh"; -- last semi-colon optional
           }
```
# Recursion
It is possible to define the first few terms of a recurrence relation by stating their `n`. For example in the perrin sequence the first terms are 3, 0 and 2 and the recurrence relation is 
$$
P_{n} = P_{n-3} + P_{n-2}
$$
Thus the function can be expressed as below:
```Haskell
perrin 1 = 3
perrin 2 = 0
perrin 3 = 2
perrin n = perrin (n-3) + perrin (n-2)
```