# Glossy MVC
Much like OOP, there are also design patterns in Haskell. The MVC is
- Model
- View 
- Controller 
```Haskell
data Model = ...
View :: Model -> Picture
Controller :: Event -> Model -> Model
```

Gloss is a 2D graphics library that can be used in Haskell. Under the hood, gloss uses OpenGL: https://hackage.haskell.org/package/gloss. Gloss uses 2D graphics, handling user input and time-dependent state updates.

Gloss can help you with monolithic 2D games like  chess, snake etc... but what about the problem of interactions between objects like in OOP?

A solution to this is using an ECS:
 - Entities - Indexes (e.g. entity 1, entitiy 2)
 - Components - Data for entities (e.g. HP, position etc,)
 - Systems - Functions over sets of components (possibly using monads e.g. for all entities with HP and position)

An ECS library in haskell is apecs: https://hackage.haskell.org/package/apecs