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
Where `x` would equal `3` and the remaining list (tail) of the list would be `[2,1]`. In this case `[3]` would be returned. 