The presence of custom data types and polymorphism motivates why the need for something called classes. Consider the following custom data types:
```Haskell
data Player = White | Black
data PieceType = Pawn | Knight | Bishop | Rook | Queen | King
```
Consider the case of needing to write an equality function over the data types:
```Haskell
eqPlayer :: Player -> Player -> Bool
eqPieceType :: PieceType -> PieceType -> Bool
eqPlayer = undefined
...
```
Writing such functions is not very efficient and can be rather laborious.

The issue compounds when considering polymorphic ADTs such as lists:
```Haskell
data List a = Empty | Cons a (List a)
eqList :: List a -> List a -> Bool
eqList Empty Empty = True
eqList (Cons x xs) (Cons y ys) = eqList xs ys && undefined
```

However type classes solve this issue. The presence of custom data types and polymorphism makes type classes useful for saving namespaces but also providing function overloading. Thus the function 

Thus for our above equation we can define the `===` operator with a type class of `Equality`. The function body for this operator would be `a -> a -> Bool`. Notice the function is also polymorphic. 
```Haskell
class Equality a where
  (===) :: a -> a -> Bool
```
It is very similar to operator overloading in C++.

It is then possible to then use the 