# Prequisites

# References
Learn You Haskell For Great Good

# Basics
Function:
```
doubleMe x = 2 * x
multiplyUs x y = x * y

doubleMe 10 // 20
```
Functions only take one parameter at a time even if it appears they are taking multiple parameters.  Currying is used heavily in Haskell.  For example `f(a, b)` can be thought of as `g(b)` where `g = h(a)`.

example of currying:
```
add x y = x + y
addThree = add 3
addThree 10 // 13
```

conditional:
```
doubleIfSmall x = if x < 100
                   then 2 * x
                   else x
```
lists:
```
// concat
[1,2] ++ [3, 4] // [1, 2, 3, 4]
// concat single item
5 : [6,7] // [5,6,7]
// index of
[1, 2, 3] !! 0 // [0]
// ranges
[5, 4 .. 1]  // [5, 4, 3, 2, 1]
```
A string is just a list of type Char.

list comprehension:
```
[ x | x <- [1..10], 2*x >= 12]]
// [12, 14, 16, 18, 20]
```
which is 
$\{x | x \in [1..10] \text{ where } 2 * x >= 12\}$

```
[ x*y | x <- [1, 2, 3], y <- [4, 5, 6], x*y < 15, x + y < 8]

// [4, 5, 6, 8]
```
which is 
$\{x*y | x \in [1,2,3] \text{ and } y \in [4, 5, 6] \text{ where } x * y < 15 \text{ and } x + y < 8\}$
Use `_` to discard some value:
```
customLength xs = sum [1 | _ <- xs]
```

Tuples can contain different values but their size matters.  `(1, 2)` is different from `(1, 2, 3)`.

# More Functions
pattern matching:
```
myHead [] = error "Can't get head of empty list"
myHead (x:_) = x
```
guards:
```
bmiSay bmi
  | bmi <= 18.5 = "underweight"
  | bmi <= 25.0 = "normal"
  | bmi <= 30.0 = "overweight"
  | otherwise = "obese"
```

using `where`:
```
initialize firstname lastname = [f] ++ ". " ++ "[l]" ++ "."
    where (f:_) = firstname
          (l:_) = lastname
```

`where` is used at the end of a function.  `let` is used in a specific scope.

`case`:
```
myHead xs = case xs of [] -> error "Can't get head of empty list"
                       (x:_) -> x_
```

`lambda`:
```
\a b -> a + b
```

# Commonly Used
`map` maps a list to another list. `filter` filters items out of an array.  `fold` maps a list to a value.

Example of fold:
```
myMaximum = foldl (\acc x -> if x > acc then x else acc)
myMaximum 0 [1, 2, 3] \\ 3
```

You can fold from the right or left.  You can use `foldr1` or `foldl1` to set the accumulator to the identity element.

`$` can be used to force the right side before the left:
```
sqrt $ 3 + 4 + 9 // 4
```

# Types and Type Classes 
Functions work on some `type class`.  A `type class` is some group of classes with some condition.  A `type class` can be thought of as an interface.

`data` can be used to define a type:
```
data MyBool = False | True
```
constructor for a type:
```
// example has two value parameters of type Float which
// create a type of Coordinate
data Coordinate = Coordinate Float Float
```
constructor with name lookup:
```
data Person = Person {firstName :: String
                      , lastName :: String
                      , age :: INT
                      }
```
type parameters (like C++ template):
```
data Vector a = Vector a a a // can be Vector Int, Vector Float, etc.
```
operations on types:
```
(Vector a b c) `vplus` (Vector d e f) = Vector (a+d) (b+e) (c+f)
```
stating that some type belongs to a typeclass:
```
data Person = Person {firstName :: String
                     , lastName :: String
                     , age :: INT
                     } deriving (EQ)  \\ Person derives Equals
```
type synonym:
```
type String = [Char]
```
`class` can be used to make a  type class:
```
class Eq a where  
    (==) :: a -> a -> Bool  
    (/=) :: a -> a -> Bool  
    x == y = not (x /= y)  
    x /= y = not (x == y)
```
`instance` is used to show how some type uses some type class:
```
data TrafficLight = Red | Yellow | Green
instance Eq TrafficLight where  
    Red == Red = True  
    Green == Green = True  
    Yellow == Yellow = True  
    _ == _ = False
```
class constraint for instance:
```
instance (Eq m) => Eq (Maybe m) where  
    Just x == Just y = x == y  
    Nothing == Nothing = True  
    _ == _ = False
```

# Functors
A `functor` is a type that can be mapped over.  A type that is a functor should implement the `Functor` typeclass and implement the `fmap` method that maps from one concrete class to another concrete class. `fmap` is a function that takes a function and a functor and then maps the function over the functor.

A functor should have an identity and it should be associative.  Entities with these two properties (identity + associative) are called monoids.

Functors can also be functions.  For example:
```
fmap (*) [1, 2, 3, 4]
```
maps a functions that takes two parameters over some integers and maps the integers to a new collection of functors, in this case the new collection of functors are functions of `[(*)1, (*)2, (*)3, (*)4)]`.

An applicative functor is a functor that contains function which can be mapped over.  `[(*)1, (*)2, (*)3, (*)4)]` is an applicative functor.i

A monad is a type that when operated on wraps it's return value in the monad type.  For example:
```
(*) Maybe a = Maybe (*) a
```

[//]: # TODO: Check if this section is correct.  applicative functor and monads description are probably wrong.

# Modules
import a module:
```
import Data.Set  \\ imports Data.Set
import Data.List (nub, sort) \\ imports nub and sort from Data.List
import Data.List hiding (nub) \\ imports everything from Data.List
                              \\ except for nub
import qualified Data.Map \\ import Data.List but force calls to it's 
                          \\ reference to require fully qualified
                          \\ names
import qualified Data.Char As C \\ use C.xxx to refer to items in
                                \\ Data.Char
```
to create a module:
```
module myModuleName
( myFunctionOne
, myFunctionTwo
, myCoordinate
) where

myFunctionOne x = x + 10
myFunctionTwo x = x * 10
data myCoordinate = myCoordinate Float Float
```

# Examples

quick sort:
```
quicksort [] = []  
quicksort (x:xs) =   
    let smallerSorted = quicksort [a | a <- xs, a <= x]  
        biggerSorted = quicksort [a | a <- xs, a > x]  
    in  smallerSorted ++ [x] ++ biggerSorted
```

