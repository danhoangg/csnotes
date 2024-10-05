Subject/Topics: #OS #MemoryManagement
[[Operating System (part 1)]]

#### Memory Management

- Makes user think there are an arbitrary number of processes running at the same time
- To make every process think it has infinite memory
	- Entire address space, 32 bit machine = 4Gb
	- Entire address space, 64 bit machines = 16Eb (Exa = $10^{18}$)
- Virtual memory does just this
- This includes
	- Swapping
	- Partitioning
	- Paging
	- Virtual memory

##### Swapping
- OS stores a queue of processes wanting to execute
	- Processes on the disk, queue in the kernal
- Processes are loaded into memory as space becomes available
- When process finishes, it is removed
- A process may also be swapped if it is stalled

##### Partitioning
- Fixed size memory partitions
	- Easy to administer
	- Logarithmic distribution of partition sizes is best
- Variable size memory partitions
	- Memory is allocated as required
	- Fragmentation makes it harder to load incoming processes

##### Physical and logical addresses
- A reloaded process is unlikely to be loaded in the same place each time
- Process = instruction + data
	- Instruction contains addresses of data elements and the addresses of other instructions
	- Data has to go somewhere
- Distinguish between 
	- Logical addresses (relative to the beginning of the program)
	- Physical addresses (actual location in memory)
- Both are reconciled at execution

#### Paging
- Fixed and variable size partitions are inefficient
- Divide physical memory into lots of small equal chunks
- Divide process into chunks

#### Virtual Memory
- Can now load processes larger than the physical memory
- Pages swap in and out as required
- We need a table of offsets for each page 
- Logical addresses now refer to a page and page table translates the base address to the physical address

##### Demand Paging
- Each thread of each process can only be in one place at one time
- As long as that instruction is in memory, the process can run 
- Access to any other page creates a page fault
	- OS needs to go and fetch another page
- Too much of this is called page thrashing

**Page tables**
- One page table per process
- When a page is active, the relevant part of the page table must be accessible

- The page table can be in 
	- The translation lookaside buffer
	- Main memory
	- Disk
- The required data can be in
	- Memory cache
	- Main memory
	- Disk
- The whole point of virtual memory is to pre-emptively get the required data into the most accessible place

##### Segmentation
- Segmentation is visible to the user
- Segmentation allows the programmer to view the memory as a set of independent address spaces
- Each segment can have different access rights and privileges
- Fragments of a process can be modified independently
- Data/ cache sharing: multiple processes can be allowed qualified access to a segment