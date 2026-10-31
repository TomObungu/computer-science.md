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
## `undefined`
Much like how in C you can have placeholder values for function in the manner of `return` or `return NULL`. In Haskell you can use a placeholder function called `undefined` that essentially states "I haven't implemented this yet"
```Haskell
calcTip :: Double -> Double
calcTip = undefined
```
## `fst`
`fst` is a function that returns the first value of a pair. Imagine you declare a function `pairFirsts` with pair types `(Int, Bool)` and `(String, Double)`. When given the input pairs `p1` and `p2`, the function will always return the `Int` of the first pair and the `Bool` or the second pair
```Haskell
pairFirsts :: (Int, Bool) -> (String, Double) -> (Int, String)
```
## Comma separation
You can type two things at once with the following syntax
```Haskell
t,f :: Bool
```
## Integer limits
In Haskell, the maximum largest integer that can be represented using the `Int` is capped at the 32-bit integer limit of $2^{32}-1$, 
```Haskell
intMax, intMin :: Int
intMax = 9223372036854775807 
```
### `Integer`
However using the `Intger` will allow unbounded defining of unbounded literals of greater than $2^{32}-1$
```Haskell
integer :: Integer -- Integers are unbounded literals
integer = 9223372036854775808
```
### `Word`
The word type has an integer limit of $2^{64}$. Although it's size is the same size as `Int` of using `32 bits`, it is unsigned. This is because the extra bit is used to not represent the negative sign. 
```Haskell
word :: Word
word = 18446744073709551615 
```