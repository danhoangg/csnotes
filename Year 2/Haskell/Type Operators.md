- Combinations of basic types can be done using type operators
- e.g. `(True, 'a') :: (Bool, Char)`

### Lists

To form values of list type we use the list value constructor called "cons"
`(:) :: a -> [a] -> [a]`
This says to build a list (of type a) we need an element of that type and a list of that type. We can always use the empty list to get started `[] :: [a]`. Lists are built as sequences of applications of the cons operator 
`1 : 2 : 3 : []`

`[] : []` describes a list of lists `[] : [] :: [[a]]`

### Tuples

Tuples are fixed length sequence of values with possibly different types
`(True, 1) :: (Bool, Int)`

### Functions
Given any Haskell types T and U, we can form the function type `F -> T`. Values of this type are functions that take a value of type T and return a value of type U
We use the fact that functions can be built using any type to have functions that return functions. We call these **curried functions**

```haskell
mult :: Int -> (Int -> (Int -> Int)
mult x y z = x * y * z

let f = mult 3 in
let g = f 4 in
g 5
```
Outputs 60


