	Polymorphism allows listing of any type. The opposite of polymorphism is monomorphism. 

Let's consider the list type and view it in the lens of polymorphism. 
```Haskell
data List a = Empty | Cons a (List a)
```
Here the `a` represents any type. This is what defined Polymorphism. In this case the list will either have the empty list data type of `[]` or will call the cons function and form a list of the type `a`.

