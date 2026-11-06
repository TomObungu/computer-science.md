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