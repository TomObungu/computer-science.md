In Haskell, lists are homogeneous, meaning they only store one type. In Haskell the type annotation for lists uses the `[]`. For example the code below represents a list of type `[Int]`
```Haskell
egList :: [Int]
```
# The 'Cons' constructor `:`
The `cons` constructor constructs a list from an element and an existing list to create a new list.  
```Haskell
egConsList :: [Int]
egConsList = 3 : []
```
For example in the above code, it pronounced as "3 cons empty list". It adds the integer "3" to the empty list. The cons constructor is a binary operator with two inputs. The cons constructor is also right associative. This means, it is possible to add and remove brackets around the second inputs of cons without changing anything
```Haskell
1 : (2 : (3 : [])) == 1 : 2 : 3 : []
```