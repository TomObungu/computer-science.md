Haskell is a statically typed language. This means all the types are typed at compile time. 
# Type Annotations
In Haskell, it is possible to annotate your expressions and specify the type. Below is an example of type annotations with primitive types
```Haskell
ff = False :: Bool
one = 1 :: Int
world = "world" :: String
quarter = 0.25 :: Double
```
Don't forget the `char` is defined with single quotes only
```Haskell
sneaky2 = '2' :: Char
```
It is possible to declare Pairs and Tuples in Haskell. Tuples are pairs with more than two values.
```Haskell
oneAndTrue = (1,True) :: (Int, Bool)
helloWorld = (hello, world) :: (String, String)
oneTwoThree = (1,2,3) :: (Int, Int, Int)
```
# Functions
It possible to define the type of functions using the `->` operator
```Haskell
addThree = (\x -> x + 3) :: Int -> Int
```
Bellow is an application to the function of `addThree` with full type annotations. In this case the expression being called is `addThree 4` but each term is fully type annotated.
```Haskell
appAddThree = ((addThree :: Int -> Int) (4 :: Int)) :: Int
```
# Type Synonyms
It is possible to have user defined types like `typedefs` in `C` using the `type` keyword
```Haskell
type Price = Double
price :: Price
price = 19.99
```
