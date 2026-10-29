ADTs are Haskell's way of making data representations. To define an ADT user the keyword `data`.  ADTs are so convenient that the `Bool` data type are not inbuilt special data types but they are just defined as ADTs. 
```Haskell
data Bool = True | False
	derving Show
```
# Sums
Data types that offer choice of disjoint values are known as Sum types. Sums are a component of ADTs. A sum type is a collection of disjoint values. Sum types are distinguished using the `|` operator. For example take a look at:
```Haskell
data Player = White | Black
```
The `Player` data type can be distinguished as either White or Black. Below are the possible values of this type:
```Haskell
white :: Player
white = White
black :: Player
black = Black
```
Defining a `Player` type would look like this
```Haskell
showPlayer :: Player -> String
showPlayer White = "W"
showPlayer Black = "B"
```
It is also possible to use pattern matching on an ADT. For example the code below pattern matches and only returns `True` if both the types are the same
```Haskell
eqPlayer :: Player -> Player -> Bool
eqPlayer White White = True
eqPlayer Black Black = True
```
Below is another example of a sum type 
```Haskell
data PieceType = Pawn | Knight | Bishop | Rook | Queen | King
```
This type represents chess pieces. 
# Products
The other part of ADTs is product types, product types allow a data type to represent a collection of things together. They are a generalisation of tuples. Consider the running example of the chess pieces. The below code utilises a product type constructor.
```Haskell
data Piece = MkPiece Player PieceType
```
The `MKPiece` constructor can be evaluated as below:
```Haskell
MkPiece :: Player -> PieceType -> Piece`
```
## Type punning
It is also possible to have the type and the constructor share the same name
```Haskell
data Piece' = Piece' Player PieceType
```
From the above piece it is possible to define a variable using the ADT in the format below:
```Haskell
whiteQueen :: Piece
whiteQueen = MkPiece White Queen
```
## Pattern matching on Products
It is then possible to pattern match on product types as below. For example the function takes in a Piece and changes the piece type to `Queen`
```Haskell
promoteToQueen :: Piece -> Piece
promoteToQueen (MkPiece c Pawn) = MkPiece c Queen
```

## Records
Records allow naming of parts of a product type
```Haskell
data PieceR = MkPieceR { player :: Player, pieceType :: PieceType }
```
Now when defining the constructor, the name of the product are clearly defined
```Haskell
blackQueen = MkPieceR Black Queen
```
