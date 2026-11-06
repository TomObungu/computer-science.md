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

Gloss can help you with monolithic 2D games like  chess, snake etc.. 