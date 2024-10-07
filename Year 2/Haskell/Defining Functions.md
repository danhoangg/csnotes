### Basic Form
`function-name arg1 ... argN = body-expression`

e.g.
```haskell
splitAt :: Int -> [a] -> ( [a], [a] )
splitAt n xs = (take n xs, drop n xs)
```


