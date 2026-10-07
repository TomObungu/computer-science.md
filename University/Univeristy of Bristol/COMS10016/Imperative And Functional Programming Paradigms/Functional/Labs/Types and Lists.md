1.1.  (a) 
```Haskell
expression :: Bool -> Int -> Int -> Int
```
(b) This is what my friend Alan wrote
```Haskell
expression :: (Num a) => Bool -> a -> a -> a
expression :: Bool -> Int -> Int -> Int
```
(c) 
I compiled this code using `gchi` and this is what the output in the shell was
```Haskell
expression :: Bool -> Int -> Int -> Int
expression = \x -> \y -> \z -> 
    if x then y + 1 else z + 1
```
``
```shell
ghci> expression True 6 7 
7
```

1.2 