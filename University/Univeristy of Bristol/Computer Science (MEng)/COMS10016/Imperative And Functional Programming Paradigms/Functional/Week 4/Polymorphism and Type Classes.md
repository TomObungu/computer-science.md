Polymorphism allows listing of any type. The opposite of polymorphism is monomorphism. 

Let's consider the list type and view it in the lens of polymorphism
```Haskell
data List a = Empty | Cons a (List a)
```
Here the `a` represents any type. 