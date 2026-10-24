It is possible to initialise a list as a tuple in Haskell. However tuples are fixed lengths and types. An example of this is below
```Haskell
egTuple::(int, char,bool)
```
It is possible assign to a tuple using 
```Haskell
egTuple = (2,'a', False)
```

It is possible to initialise a list with a type using the `[]`
```Haskell
egList::[int]
```
To create a list, use the `=` operator and the `:`
```Haskell
egList = 1:2:3:4
```

## List constructors
It is possible to construct lists using the `[]` constructors.  By defining its type and then assigning it like this
```Haskell
egEmptyList :: [Int]
egEmptyList = []
```

It is also possible to use the 'cons' constructor `:` like this. The cons constructor initialises a list and adds `1` to the list. 
```Haskell
egConsList :: [Int]
egConsList = 1 : []
```

# Pattern Matching on lists
Consider the Haskell code below:
```Haskell
is123 :: [Int] -> Bool 
is123 xs = case xs of 
    1 : 2 : 3 : [] -> True
    _ -> False
```
This code below initialses a function that takes in a an integer and returns a true value.  Afterwards the case statements can take in the list instead
```
-- >>> is123 [1,2,3,4]
-- False
```
Using the pattern matching on the list `[1,2,3,4]` will yield false. 
Consider the Haskell code below:
```Haskell
head :: [Int] -> Int
head xs = case xs of
    x : xs' -> x
```
Running this code in the IDE will yield and error stating that there is an ambiguous variable within the header `Prelude`.
```Haskell
head :: [Int] -> Int
head xs = case xs of
    x : xs' -> x
```
It is possible to hide variables that have the same name as keywords within functions:
```Haskell
import Prelude hiding (head)
```

# Syntax sugar
The Haskell code:
```Haskell
1 : 2 : 3 : []
```
and
```Haskell
[1,2,3]
```
are synonymous.

## Partial and full functions
Below is a non-partial function as it covers the domain for other cases using the `_` operator
```Haskell
egListSugarMatch :: [Int] -> Int
egListSugarMatch [x,y,z] = x + z
-- Consider every other case value to ensure the function is not a partial function
egListSugarMatch _ = 0;
```
The function below uses pattern matching on lists with arbitrary varaibles and returns its length
```Haskell
isLength3 :: [Int] -> Bool
isLength3 listType = case listType of 
    [x,y,z] -> True
    _ -> False
```