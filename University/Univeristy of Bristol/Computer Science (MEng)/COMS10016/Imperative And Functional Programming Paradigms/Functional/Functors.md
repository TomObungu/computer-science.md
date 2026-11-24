Functors are a generalisation of `map` for other types. Applying functions into a context whilst preserving structure. The structure remains the same however the elements within the structure changes.
```Haskell
class Functor f where
	fmap :: (a -> b) -> f a -> f b
	fmap = map
```
Consider the instance of the `[]` case with functors
```Haskell
instance Functor [] where
	fmap :: (a -> b) -> 
```