# Types
1.1.  
(a) 
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
(a)
```Haskell
(even n) :: Bool
even n :: Int -> Bool,
n :: Int, 
(div n 2) -> Int 
div :: Int -> Int ->Int
((3 * n) + 1) :: Int
(3 * n) :: Int
3 :: Int
1 :: Int
(+) :: Int -> Int -> Int
```
(b) Alan included the entire expression
```Haskell
(if even n then div n 2 else (3 * n) + 1)) :: Int
```

# Pattern Matching on Lists
2.1 
```Haskell
headOrZero :: [Int] -> Int
headOrZero xs = case xs of
    [] -> 0
    x : xs' -> x
```
2.2
```Haskell
length :: [Int] -> Int 
length [] = 0
length (_ : xs ) = 1 + length xs
```
2.3 
