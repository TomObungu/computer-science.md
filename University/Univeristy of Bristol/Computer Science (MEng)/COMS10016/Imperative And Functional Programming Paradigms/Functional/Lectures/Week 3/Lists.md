In Haskell, lists are homogeneous, meaning they only store one type. In Haskell the type annotation for lists uses the `[]`. For example the code below represents a list of type `[Int]`
```Haskell
egList :: [Int]
```
# The 'Cons' constructor / semicolon operator `:`
The `cons` constructor constructs a list from an element and an existing list to create a new list.  
```Haskell
egConsList :: [Int]
egConsList = 3 : []
```
For example in the above code, it pronounced as "3 cons empty list". It adds the integer "3" to the empty list. The cons constructor is a binary operator with two inputs. The cons constructor is also right associative. This means, it is possible to add and remove brackets around the second inputs of cons without changing anything
```Haskell
1 : (2 : (3 : [])) == 1 : 2 : 3 : []
```

The `:` operator defines how to create data AND also pattern match on it. For example the following function on lists allows pattern matching. It first creates a list \[1,2,3\] and the compares it with the variable `xs`. If `xs` matches the list \[1,2,3\] then it will compare it. 
```Haskell
is123 :: [Int] -> Bool
is123 xs = case xs of
  1 : 2 : 3 : [] -> True
  _ -> False
```
## head and tail
The `:` allows splitting of lists. For example if we are writing a function, it possible to split the the list into the first element of the list and the rest of the list. 
```Haskell
myFunc :: [Int]
my ( x : xs ) = x
```
For example in the function above, if the example function is called
```Haskell
myFunc [3,2,1]
```
The example list is evaluated as:
```Haskell
[3] : [2,1]
```
Where `x` (head) would equal `3` and the remaining list (tail) of the list would be `[2,1]`. In this case `[3]` would be returned. 

## pattern matching with `:`
It is possible to have advanced pattern matching with the `:` operator. For example if we are asked to write a function `isLength3` that determines whether a list has length `3`.
```Haskell
isLength3 :: [Int] -> Bool
```
It possible to use the `_` operator and the cons `:` operator to pattern for any 3 items in the list. Beware the key part of this is that the constructor must end in `[]` to show that the list a bound list of only 3 elements
```Haskell
isLength3EgSolution :: [Int] -> Bool
isLength3EgSolution (_ : _ : _ : []) = True
isLength3EgSolution _ = False
```
Recall that the list is has the default clause of `_` to prevent the function from being a partial function. 
# Recursive List Functions
There are two cases we need to think about when writing recursive functions. We need to think about the base case 