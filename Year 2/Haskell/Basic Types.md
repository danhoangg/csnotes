Haskell is **strongly statically typed** which means that types are checked at compile type and the compiler will throw an error if it finds problems with the way typed values are being used.

if evaluating an expression **e** would produce a value a of type **t**, then **e** has type **t** written
`e :: t`

**Basic types**
`Bool Char String Int Integer Float`
**Compound Types** built from the basic types by combining them using **type operators** e.g.
- List Types
- Function Types
- Pair (or Tuple) Types

`Bool`
- Size 1 bit, holds value either `True` or `False`
- `&& :: Bool -> Bool -> Bool` is a function type

`Char`
- `'a' :: Char`
- `'5' :: Char`
- `'\x2588' :: Char`

`String`
- `"hello" :: [Char]`
- `"this is\neasy" :: [Char]`
- Functions that work on list can be applied to strings, `length "abcde"`

