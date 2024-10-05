Subject/Topics: #OS #MemoryManagement
[[Operating System (part 2)]]

- Two main families:
	- Microsoft Windows
	- Unix-like
- The OS is just a program
- Essential function is to hide complexity from programmers and users

**Concealing complexity**
- The task of most software
- To protect users and programmers from having to work with horrendous complexity
	- Internet protocols
	- Compilers
	- Device drivers

- Prove an interface to the hardware, so that other programs can make effective use of the computer
- This works much better if the hardware provides support for the OS

#### OS Kernel Services

- Memory management
	- Allocate memory to programs
	- Manage virtual memory
	- Protect against programming errors and malware
- Task management
	- Launch processes
	- Maintain process table
	- Carry out timeslicing
	- Handle interrupts
	- Set program privilege levels
- File management
	- Respond to program requests to open, read, write and close files
	- Set and check permissions
	- Handle buffering
- Device management
	- Use device drivers to respond to program requests to open, read, write and close devices such as printers, cameras, displays, keyboard...


#### Essential hardware features for an OS

- Memory protection
	- Protect the OS
	- Allow OS to protect programs from each other
- Timer
	- Prevent a job monopolising the system
- Privileged instructions
	- Only executed by OS, e.g. I/O
- Interrupts
	- Allow for relinquishing and regaining control

#### Scheduling

- Making effective use of the processor
- Central facts:
	- Memory access is very slow compared with the processor speed
	- I/O devices are extremely slow compared with the processor
	- Multiple tasks need to share the machine
	- A processor can only do one thing at a time
- While one task is waiting for an I/O device, another task should be able to use the processor

#### Processes and context switching

- A process is a running program
- A process includes (roughly)
	- Code
	- Data
	- Resources
	- Current state: registers
- *Context switching* means that the state of a running process is saved, and another process given processor resources

### Memory Management

- To make the user think there are an arbitrary number of processes running at the same time
- To make every process think it has infinite memory
	- Entire address space, 32 bit machine = 4Gb
	- Entire address space, 64 bit machine = 16Eb
- Virtual memory does just this

#### Swapping

- OS stores a queue of processes wanting to execute
	- Processes on the disk, queue in the kernel
- As space becomes available, the processes are loaded
- When a process finishes, it is removed
- A process may also be swapped out if it stalled (for example, waiting for I/O)

#### Partitioning

- Fixed size memory partitions
	- 'Typical' usage implies a logarithmic distribution of partition sizes is best
	- Easy to administer
- Variable size memory partitions 
	- Memory is allocated as required
	- Fragmentation makes it harder to load incoming processes