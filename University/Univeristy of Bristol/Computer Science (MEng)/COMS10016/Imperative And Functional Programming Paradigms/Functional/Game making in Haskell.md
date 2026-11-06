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
 - Entities - Indexes (e.g. entity 1, entity 2)
 - Components - Data for entities (e.g. HP, position etc,)
 - Systems - Functions over sets of components (possibly using monads e.g. for all entities with HP and position)

An ECS library in haskell is apecs: https://hackage.haskell.org/package/apecs

Creating Entities with components
```Haskell
newtype Position = Pos (Float, Float)
instance Component Position where type Storage Position = Map Position
```

```Haskell
newtype Velocity = Vel (Float, Float)
instance Component Velocity where type Storage Velocity = Map Velocity
```

```Haskell
createEntities :: System' ()
createEntities = do
	newEntity_ (Pos (0,0) Vel (10,10))
	newEntity_ (Pos (50,50) Bel (-10,))
```

```Haskell
newEntity_
	:: Set' component
	=> component -> System'
```

```Haskell
newEntity_ 
	:: (MonadIO m, Set world m component, Get world m EntitiyCounter)
	=> component -> SystemT world m ()
```

 
Creating Systems:
```Haskell
stepPos :: Float -> System' ()
stepPos dt 
	= cmap (\(Pos (x,y), Vel(vX, vY)))
		-> Pos (x + vX * dt, y + vY * dt))
```

```Haskell
cmap 
	:: (Get' cx, Members' cx, Set' cy)
	=> (cx -> cy) -> System'()
```

You can use a language extension called `TemplateHaskell` and gloss to form a model. Remember to `import Apecs.Gloss`. 
```Haskell
makeWord "Model" [''Camera, ''Position, ''Velocity]
```

```Haskell
view :: System Model Picture
view 
	= foldDraw (\(Pos (x,y))
		-> translateCircle x y (Circle 10)
```

You can use pattern matching on inputControllers
```Haskell
inputController :: Event -> System Model ()
inputController event = case event of 
	EventKey (SpecialKey  KeyEsc) DOwn _ _ -> liftIO exit
```