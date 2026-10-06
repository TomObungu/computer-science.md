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