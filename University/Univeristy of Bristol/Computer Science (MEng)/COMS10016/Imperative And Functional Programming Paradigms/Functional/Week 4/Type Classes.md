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
```