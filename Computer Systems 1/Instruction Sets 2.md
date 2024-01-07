Subjects/ Topics: #CPU #Instructions #Assembly 
[[Instruction Sets]]

- Different instruction set architectures have different instruction sets
- Different microarchitectures may share an instruction set
- Usually represented in assembly language
- Instruction is made up of Opcode and a set of result/ operand references

**Four main instruction set architecture types:**
- Accumulator based
- Stack based
- Register-memory based
- Register-register 
- Memory-memory


Note-to-self: X, A and B are all locations in memory, not register
#### Accumulator ISA
- X = A + B =>
```
LOAD A
ADD B
STORE X
```
- A is loaded into the accumulator
- B is added directly from memory
- Result can then be stored in memory
- Accumulator is an input and an output store

#### Stack based ISA
- X = A + B =>
```
PUSH A
PUSH B
ADD
POP X
```
- Both operands pushed onto stack
- Result popped off the stack
- Needs a top-of-stack(TOS) pointer, or hardware stack
- Only the top of the stack is written to
- Memory transfer requires extra operations

#### Register-memory ISA
- X = A + B =>
```
LOAD  R3, A         (load A into R3)
ADD   R1, R3, B     (add R3 and B (from memory) and store in R1)
STORE R1, X         (Store R1 in X)
```
- One input <= memory
- One input <= register
- Result => register

#### Register-Register (Load/Store) ISA
- X = A + B =>
```
LOAD  R3, A
LOAD  R2, B
ADD   R1, R3, R2
STORE R1, X
```
- Operands loaded from memory into registers
- Add uses operands stored in registers
- Memory transfer requires extra operations

| Accumulator | Stack | Register |
| ---- | ---- | ---- |
| Short instructions | Simple Model | Easy code generation |
| One implicit operand, one explicit | Short instructions | Clever compile optimisations |
|  | Implicit operands | Fast access to temp values |
| BUT | BUT | BUT |
| Single temporary storage location  | The stack cannot be randomly accessed | Operands must be named |
| High memory traffic | Stack becomes a bottleneck | Longer instructions |

**Register-Memory or Register-Register**

| Register-Memory | Register-Register |
| ---- | ---- |
| Simple code generation | Fixed-size instructions (simple encoding) |
| Data can be accessed directly from memory | Simple code generation |
|  | Instructions require a similar known number of cycles |
|  | Fast |
| BUT | BUT |
| Functionally commutative operations, non-commutative behaviour (source operand can be destroyed) | High instruction count |
| Instructions require a variable number of cycles (memory access can be slow) |  |

#### Memory-Memory ISA
- Produces compact code
- Large variation in instruction size
- Large variation in execution time per instruction
- Memory access is the bottleneck
- Not used today

### More Registers?

- May need longer instructions
	- more bits to encode
- means more to save on context switch
- increases cost
- increases complexity

**Which ISA is best**
- It depends
- There's a trade off
	- Instruction complexity for code size
- *If RISC-based ISAs give better performance-per-watt than CISC, why did x86 (a CISC architecture) dominate?*

