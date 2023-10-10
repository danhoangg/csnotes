### Algebra
Operators operate on values to produce more values:
- **Operators** are also called functions
- **Operands** are also called arguments

#### Karnaugh Maps

**Implicant** - A term covering at least one 1 element of a function and no 0 elements
**Prime Implicant** - An implicant that cannot be covered by any other implicants
**Essential Prime Implicant** - A prime implicant that contains at least one 1 element that is not covered by any other prime implicants

You can put an X into a karnuagh map for values that don't matter
![[xinkmap.png]]

We can group X with 1 as we don't care about that input so the output of the karnaugh map will be bd


#### Adders

Half adder:
- Don't take carry as an input, adds 2 binary numbers
- XOR gate

Full Adder:
- Takes A,B and carry as input and outputs result as well as carry out
- If there are at least 2 1s then there will be a carry, therefore Cout = AB + ACin + BCin
- The output can be added together therefore 3-input XOR