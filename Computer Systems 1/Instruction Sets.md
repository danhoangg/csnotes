Subjects/ Topics: #CPU #Assembly #Instructions

- At a high level, an instruction set is a list of all the commands that a processor can execute
- Different instruction set architectures have different instruction sets, e.g. ARM and x86
- Different microarchitectures may share an instruction set. e.g. Intel Core and AMD Ryzen

**Machine Code:**
- This is what is executed
- Binary
- Usually represented by assembly language
	- One line of assembly (typically) produces one machine instruction

- Fetch
	- Get instruction from memory
- Decode
	- Work out what the instruction is
- Execute
	- Run it

**Instruction Types:**
- Data processing
- Data movement (read/ write main memory)
- Program flow control

**ALU: Arithmetic instructions**
- Add, subtract, multiply, divide
- Could be (signed) integer or floating point
- May include
	- Absolute
	- Increment
	- Decrement
	- Negate
- Shift and rotate
	- Bit masks
	- Unpacking data
	- Fast integer arithmetic
	- Rotating is useful for tasks e.g. cryptography
	- 1 bit right rotate on 0111 -> 1011

**Control Transfer Instructions**
- Control program flow
	- Allow for conditional expressions
- Branch
- Skip
- Subroutine
- Loop

**More addresses**
- More complex instructions
- More registers
- Register-to-register operations are quicker
- Fewer instructions per program
**Fewer addresses**
- Less complex instructions
- More instructions per program
- Faster fetch/execution of instructions

#### RISC vs CISC

CISC - Complex instructions that do a lot of work
RISC - Simpler instructions, but more of them to do the same work

#### Endianness

- How are bytes in a word ordered
- How are bits in a byte ordered
- No consistency or consensus
- Can be a problem at low level or communicating between systems that do it differently

Consider the 32 bit hex literal 0x12345678, stored byte aligned at 0x900
![[Endian.png]]

- Field addresses are the same for both schemes
- Big endian memory dumps are left to right
	- Easy for western readers
- Big endian machines store character strings and integers in the same order (MSB first)
- Big endian has to perform an extra operation when converting from a 32 to a 16 bit address