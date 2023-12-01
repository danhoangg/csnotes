Subjects/ Topics: #RAM #Cache #MemoryManagement 

**Memory characteristics:**
- Location
- Capacity
- Unit of transfer
- Access method
- Performance
- Organisation

#### Capacity
Normally expressed as bytes
- 1KiB = 1024 bytes
- 1MiB = 1024 * 1024 bytes

Unit of transfer:
- Internal
	- Governed by data bus width
- External
	- A block much larger than a word
- Addressable unit
	- Smallest location which can be uniquely addressed

#### Performance
- Access time
	- Time between presenting the address and getting the valid data
- Memory cycle time
	- Time may be recovered for memory to 'recover' before next access
- Transfer rate
	- Rate at which data can be moved

#### Physical types
- Semiconductor
	- SRAM
	- DRAM
	- Flash
- Magnetic, bubble, etc

#### Physical characteristics
- Decay
- Volatility
- Erasable
- Power consumption

**Storage heirarchy list:**
- Registers
- L1 cache
- L2 cache
- Main memory
- Disk cache
- Disk, flash/SSD
- Optical
- Tape

#### Dynamic RAM (DRAM)
- Bits are stored as charge in a capacitor
- Charges leak so needs refreshing even when powered on
- Simple construction
- Smaller per bit
- Less expensive
- Slower
- Used in main memory

#### Static RAM
- Bits stored as on/off gates
- No charges to leak
- More complex construction
- More expensive per MiB
- Faster
- Good for cache and embedded RAM

#### ROM 
- Permanent storage
- Hardware supports library subroutines
- System programs (BIOS)

#### Error correction
- DRAM can lose data
- Hard failure
	- Permanent defect
- Soft error
	- Random, non-destructive
	- No permanent damage
- Detected using error correcting code


#### Caches
CPU needs data faster than DRAM can provide
- Cache are small blocks of SRAM located on CPU chip
- Memory requests go there

**Cache operation**
- CPU wants a memory location
- Address goes to cache
- If cache can provide it, return it back (cache hit)
- Otherwise read required block from main memory (cache miss)

**Cache design parameters:**
- Size
- Mapping function
- Replacement algorithm
- Write policy
- Block size
- Number of caches

**Three level caches**
Multiple core CPUs usually share a large level 3 cache to 'shield' RAM from cores
This is a typical design
![[3 level cache.png]]

##### Cache mapping function
- Needed because cache is smaller than RAM
- Blocks of cache are allocated to certain addresses
- Simplest method - direct mapped
- Most caches now associative

**Direct mapping**
- Each block of main memory maps to only 1 cache line
- Address in two parts
- Least significant w bit identify unique word
- Most significant s bit specify one memory block

**Associative mapping**
- A main memory block can load into any line of cache or at least a set of lines
- Memory address is interpreted as tag and word
- Tag uniquely identifies block of memory
- Every line's tag is used for a match