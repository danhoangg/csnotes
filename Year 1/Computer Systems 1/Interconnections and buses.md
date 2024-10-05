 Subjects/ Topics: #CPU #RAM #Buses

**Interconnection Structure**
Different type of connections required for different type of unit:
- Memory
- Input/Output
- CPU

#### Memory Connection
- Consists of N words of equal length with unique addresses
- Memory
	- Receives and sends data
	- Receives addresses
	- Receives control signals
		- Read
		- Write
		- Timing

#### Input/Output connection
- Similar to memory from computer's viewpoint
- Many I/O modules use a standard bus now

#### CPU Connection
- Reads instructions and data
- Writes out data
- Sends control signals
- Receives interrupts

## Buses

- Some look like parallel lines on circuit board
- Some are serial interconnections

**Three types of bus lines**
- Data lines
- Address lines
- Control lines

### Address bus
- Identify the source or destination of data
- Bus width determines maximum memory capacity of a system

### Control bus
- Control and timing information
- Typical control lines includes:
	- Memory read/write signal
	- I/O Port read/write signal
	- Transfer Acknowledgement
	- Bus request/grant
	- Interrupt request/acknowledgement
	- Clock signals
	- Reset

**To use a bus, a module has to:**
1. Obtain the use of the bus
	1. Only one module can use the bus at any one time
	2. Bus control is handled through Arbritation
2. Transfer data and/or requests
	1. Data and instructions may be on dedicated lines
	2. Multiplexing necessary if data share lines
3. Synchronise and/or acknowledge
	1. Ensure recipient is ready for data
	2. Ensure recipient received data

#### Single bus problems

- Lots of propagation delay
- Different devices may work at different speeds
- Most systems use multiple buses

### PCI express: PCIe
- Serial bus with multi GB lanes
- Use more lanes for a GPU card

**NVM express**
- Directly attached to PCIe

### Hard disk connectivity
- SATA - serial bus 3-6 Gb
- SAS (servers) 12 Gbit/s
- Fibre channel - can pass other protocols

**SCSI** - used in server storage
**Universal Serial Bus (USB)**:
- Ideal for low speed to high I/O devices
- Expandable

