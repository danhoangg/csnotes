#### Basic mathematical functions
```
> 2+3*4
14

> (2+3)*4
20
```
```haskell
3 * 7
(*) 3 7

mod 10 2
10 `mod` 2
```

#### List functions
```haskell
> head [1, 2, 3, 4, 5]
1

> tail [1, 2, 3, 4, 5]
[2, 3, 4, 5]

> length [1, 2, 3, 4, 5]
5

> [1, 2, 3, 4, 5] !! 2
3

> take 3 [1, 2, 3, 4, 5]
[1, 2, 3]

> drop 3 [1, 2, 3, 4, 5]
[4, 5]

> [1, 2, 3] ++ [4, 5]
[1, 2, 3, 4, 5]

> sum [1, 2, 3, 4, 5]
15

> product [1, 2, 3, 4, 5]
120

> reverse [1, 2, 3, 4, 5]
[5, 4, 3, 2, 1]

> repeat 1
[1, 1, 1, ...]
```
#### Applying functions
```haskell
f a b + c * d
```
Is equal to $f(a, b) + cd$
```haskell
f a + b
means (f a) + b

f a b c
means ((f a) b) c
```
#### Defining functions
```haskell
double x = x + x
quadruple x = double (double x)

factorial n = product [1..n]
average ns = sum ns `div` length ns
```
Function and argument names must start with a lowercase letter.
You can also define new operators and use symbols to name them
```haskell
> (£) x y = x + y
> 5 £ 6
11
```
And by convention, list arguments end with an s: `ls, xs, ns`
