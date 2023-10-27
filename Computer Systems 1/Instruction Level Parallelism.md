
### Superscalar

- Common instructions can be initiated and executed independently 
- Most operations are on scalar quantities, not arrays or vectors
- Overall improvement
- Limitations:
	- Instruction level parallelism
	- Compiler based optimisation
	- Dependencies

### Dependency limitations

**True data dependency**
```
ADD r1, r2          (Adds: r1=r1+r2)
MOVE r3, r1         (Moves r1 into r3)
```
You can't move r1 until all operations have been completed

**Procedural dependency**
```
if (x+2) > y
	y = y+1

z = x+y
```
Cannot execute instructions after a branch in parallel with instructions before a branch

**Resource conflict**

- Two or more instructions requiring access to the same resource at the same time
- Could duplicate resources


### Completions

**In-Order Issue, In-Order completion**
- Instructions executed in the order they occur
- Not very efficient
- Instructions stall if necessary

**In-Order Issue, Out-of-Order completion**
- Can't always complete different instructions at different times e.g.
```
R3 = R3 + R5 (I1)
R4 = R3 + 1  (I2)
R3 = R5 + 1  (I3)
```
- If I3 is executed before I2 then R4 will have wrong result, true data dependency

**Out-of-order issue, Out-of-order completion**

- Decouple decode pipeline from execution pipeline
- Can continue to fetch and decode until this pipeline is full
- Instructions can be executed when need be
- Processor can look ahead

