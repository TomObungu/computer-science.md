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
```Haskell
expression :: Bool -> Int -> Int -> Int
expression = \x -> \y -> \z -> 
    if x then y + 1 else z + 1
```