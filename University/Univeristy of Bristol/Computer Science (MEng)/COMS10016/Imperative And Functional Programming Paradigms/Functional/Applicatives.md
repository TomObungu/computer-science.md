![[Pasted image 20261124153043.png]]
Applicatives are applying functions within a context. Output structure depends on the input structure alone. Values cannot affect structure. Pure lifts values into a context. Preservers structure when used with `<*>`. All applicatives are also functors. 

```Haskell
class Functors f => 
```

The output structure is based only on the input structure. This is the difference between a functor and an applicative. Output structure depends on the input structure alone. 