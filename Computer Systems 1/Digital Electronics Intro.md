
### Transistors
![[MOS transistor.png]]

Allows electricity to flow or not, 1 or 0.

### Logic Gates
Computers are made of logic gates!!!!
Every gate can be made from one gate NAND (universal gate), e.g AND, OR, NOT

Truth tables can be used to check outputs for different inputs.
XOR - either or but not both

#### Adder
![[adder.png]]

### Logic laws
A.0 = A                             A+0 = 0
A.1 = 1                              A+1 = A
A.A = A                            A+A = A
A.!A = 1                            A+!A = 0

### De Morgans laws !!!!
Boolean algebra is associative, distributive and commutative

!(A+B) = !A.!B
!(A.B) = !A+!B

#### Tristate
You can't share a wire from lots of gates
Tristate gates can be bidirectional
![[bidrectional.png]]
### Karnaugh maps

Used to simplify boolean expressions

### FPGAs
- Field programmable gate arrays can have millions of gates
- up to 1GHz
- can have a CPu or DSP in already
- or "drop" a soft-core into it
- Even build from MATLAB
- Some cloud systems use them to accelerate functions

### Hardware logic
![[AND hardware.png]]
![[OR hardware.png]]