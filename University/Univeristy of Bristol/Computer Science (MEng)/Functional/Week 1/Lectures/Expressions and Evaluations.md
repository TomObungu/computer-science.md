It possible to declare variables within `ghci`like this
```Haskell
x = 1
```

It is possible to evaluate expressions within code editors like VSCode with plugins. It also possible to evaluate expressions using `ghci` on the terminal. 
```Haskell
(x + x) * 5

==> (1 + 1) * 5

==> 10
```
It possible to evaluate function by declaring the input variable to be equal to the provided argument and evaluate the body. 
```Haskell
(\x -> x + x) 5
==> {- x = 5 -} x + x
```
You can define functions like this
```Haskell
g = \x -> \y -> \z -> x + z
```
You can also define arguments like this using syntax sugar
```Haskell
g' = \x y z -> x + z
```