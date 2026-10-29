The presence of custom data types and polymorphism motivates why the need for something called classes. Consider the following custom data types:
```Haskell
data Player = White | Black
data PieceType = Pawn | Knight | Bishop | Rook | Queen | King
```
Consider the case of needing to write an equality function over the data ty