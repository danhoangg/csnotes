**Key ideas**
- Concentrate on the high-level 'functional' behaviour when writing programs
- Leave the memory management and implementation to the compiler
- Very set theory

**Summing n squares**
```haskell
sumsq n = [x^2 | x <- [1..n]]
```
**Quicksort**
```haskell
quicksort [] = []
quicksort (x : xs) = quicksort ls ++ [x] ++ quicksort rs
					where ls = [a | a <- xs, a<=x]
						  rs = [a | a <- xs, a>x]
```
