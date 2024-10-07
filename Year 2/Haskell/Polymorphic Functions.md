Expressions in Haskell can often be potentially given many different types
- `length :: [a] -> Int`
- We say that a function is polymorphic if the type contains one or more type variables

Example:
```haskell
fst :: (a,b) -> a
head :: [a] -> a
take :: [a] -> [a]
```

- Consider the function `add x y = x + y`
- It can't accept all types as it uses a `+` and therefore should only be allowed to take in Int, Integer, Float and Double
- `add :: Num a => a -> a -> a`
- Num is a type class, add accepts arguments of any type a that is an instance of the Num class

### Basic type classes
- Haskell's way of providing overloaded functions
- Haskell types may be instances of more than one class

#### Class Eq
- Represents types that support the comparison operation, e.g.
- `(==) :: a -> a -> Bool`
- `(/=) :: a -> a -> Bool`

#### Class Ord
- Represents types that support order comparisons. e.g.
- `(<) :: a -> a -> Bool`
- `(>=) :: a -> a -> Bool`
- `min :: a -> a -> a`
- `max :: a -> a -> a`

#### Class Show and Read
- Pretty printing a variable to the screen can be done using the show function
- `show :: a -> String`
- Conversely, parsing a String to a variable type can be done using read
- `read :: String -> a`

#### The number classes
- Class Num represent types that represent all numbers
	- `(+) :: a -> a -> a`
	- `(*) :: a -> a -> a`
	- `negate :: a -> a`
	- `abs :: a -> a`
- Class Integral is for Ints and Integers
	- `div :: a -> a -> a`
	- `mod :: a -> a -> a`
- Class Fractional is for Floats and Doubles
	- `(/) :: a -> a -> a`
	- `recip :: a -> a`

