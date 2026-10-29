# Polymorphic Typing

Polymorphism allows a type to work with values of different types. The opposite of polymorphism is monomorphism, where a type is fixed rather than generalised.

Let's consider the list type and view it through the lens of polymorphism.

```Haskell
data List a = Empty | Cons a (List a)
```

Here, `a` represents any type. This is what defines polymorphism in this example. The list will either be empty (`Empty`) or use the `Cons` constructor to add an element of type `a` to another list of type `List a`.

For example, we could create lists containing integers or characters:

```Haskell
intList :: List Int
intList = Cons 1 (Cons 2 Empty)

charList :: List Char
charList = Cons 'a' (Cons 'b' Empty)
```

The same `List` type can therefore represent lists of different element types. The type variable `a` is replaced by a particular type when we use the list.

## Polymorphic Algebraic Data Types

We can define our own data types that work with different types by using type variables.

For example, a pair can contain two values of the same type:

```Haskell
data Pair a = Pair a a
```

Or we can define a pair that contains two potentially different types:

```Haskell
data Pair a b = Pair a b
```

Here, `a` and `b` are independent type variables. This means that the first value and second value do not have to be the same type.

```Haskell
example :: Pair Int Char
example = Pair 10 'a'
```

We can also define a type that represents a value of either one type or another:

```Haskell
data Either a b = Left a | Right b
```

The `Left` constructor stores a value of type `a`, whereas `Right` stores a value of type `b`.

Another example is the `Maybe` type, which represents a value that might be absent:

```Haskell
data Maybe a = Nothing | Just a
```

`Nothing` represents the absence of a value, while `Just` contains a value of type `a`.

## Polymorphic Functions

Polymorphism also allows functions to work with values of different types.

For example, the length of a list does not depend on the type of its elements:

```
length :: [a] -> Int
```

The function accepts a list containing elements of any type and returns an integer representing its length.

Similarly, we can check whether a list is empty without caring about the type of its elements:

```Haskell
isEmpty :: [a] -> Bool
isEmpty [] = True
isEmpty _  = False
```

The type variable `a` means that `isEmpty` works on lists of any element type.

We can also write functions that work with pairs:

```Haskell
fst :: (a, b) -> a
snd :: (a, b) -> b
```

`fst` returns the first element of a pair, while `snd` returns the second. Notice that the two elements can have different types.

## Parametricity

A polymorphic function is constrained by its type. For example:

```
identity :: a -> a
identity x = x
```

The function receives a value of type `a` and returns a value of the same type. It cannot arbitrarily change that value into a value of another type.

# Type Classes