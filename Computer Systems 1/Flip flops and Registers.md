
**Flip-flops**:
- Stores one bit
- Synchronous digital circuits

**Registers**:
- Stores the data being worked on in CPUs
- Are the fastest type of storage
- Made of flip-flops

**Serial transmission**:
- When you send a byte across one wire

**Parallel transmission**:
- When you send a byte across multiple wires by sending one bit per wire
#### Reset-Set flip-flop (RS)
| S | R | Q$_{N+1}$   |
|---|---|-----------|
| 0 | 0 | Q$_{N}$       |
| 0 | 1 | 0         |
| 1 | 0 | 1         |
| 1 | 1 | undefined |

[Try online](https://www.falstad.com/circuit/e-nandff.html)
Every tick it will output what the last input was unless a new input is entered, in which it will change to that output until another input is entered.

#### D-type flip flops
Stores the data input for one clock cycle, state changes only when the clock is high
![[D-type flip flop.png]]

#### A basic register 
![[Register.png]]

#### Register to register copy example
![[Register copy.png]]

### Serial data transfer

Computers need to to send and receive data both serially and in parallel, e.g. input devices and serial ports need to receive and process data serially.
![[parallel serial.png]]

