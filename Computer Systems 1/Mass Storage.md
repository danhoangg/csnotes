Subjects/ Topics: #Storage #SecondaryStorage

**Types of Storage:**
- Magnetic Disks
- Solid State Disks
- Optical
- Magnetic tape

#### Magnetic Disk
- Metal/Glass/ceramic disk coated with magnetisable material (like iron oxide)
- Best value
- Concentric rings or tracks
	- Gaps between tracks
	- Reduce gap to increase capacity
	- Same bits per track
	- Constant angular velocity
- Tracks divided into sectors
- Min. block size is one sector
- Disk head is a magnetic sensor
- **HDD**
	- Universal and cheap
	- Fairly fast
	- Onboard processor/cache

- HD speed determined by:
	- Seek time
	- Rotational latency
	- Access time = seek + latency
	- Transfer rate
- HD throughput:
	- Controllers have different speeds and optimisations
	- Throughput off disk may be 150MB/s, but burst over bus faster
- On-disk cache:
	- Modern disks have 8-128MB on-board RAM buffer/cache
	- Used to store whole tracks and cache r/w
	- Acts as a buffer between disk and external I/O
- MTBF
	- Mean time between failures for hard disks is around 114 years
	- So two disks in RAID0 has half the MTBF
	- BUT if u have 100 disks you expect one to fail
	- AND double failures probable

#### Solid State Drives
- Non volatile NAND logic or Flash based
- Expensive per byte
- Fast access times
- Near "zero" latency
- More shock resistant and silent
- Lower power
- **Characteristics:**
	- Can only write approx. millions of times
		- **Wear levelling** - spreads the writes around around so one area is not worn out
		- **Overprovision** - spare storage to use if blocks fail
	- File systems consider SSD issues
		- TRIM command tell SSD which blocks are not needed and can be 'erased'
		- Erase normally only works on blocks
	- Need up to date firmware and drivers
- **Architecture**
	- Controller does interface, addressing, wear levelling, error detection/correction, bad block management
	- To change some bytes, a block needs to be read, modified and written back

- SATA is not fast enough 
- NVM Express (NVME), in M.2 format using PCIe
	- Fast
	- Supports very long command queue
- Directly attached to PCIe 2-4 lanes
- Usually have onboard RAM cache

#### Blu-ray
- Use 405nm laser - hence smaller features
- 15-30Gib still useful for offline storage/ transfer
- Can read at 70MiB/s

- Optical jukeboxes
	- Many TB per box, usually DVDr/ Blu-ray

- Magnetic Tape
	- Large 12-36TB
	- Serial access but good for backups
	- Speed often quoted in GB/hour
	- Cheap per byte

- Tape autochangers
	- Hold banks of tapes in exabytes ($10^{18}$ bytes)
	- Multiple drives 1-144
	- Required for unattended backup and cycles

- iSCSI
	- Internet small computer system interface
	- Uses tcp/ip over normal ethernet
	- Typically uses isolated network
	- Can use an offload-processor card to save CPU time
	- Allows remote and very flexible storage arrays

- SAN
	- Storage area networks
	- Like disks
	- Fast and low latency
	- Starting to use 16Gbit/s fibre channel
	- Can use 12 GB drives or even SSD

#### Redundant Array of Inexpensive Disks
- RAID
- RAID 0
	- No redundancy
	- Data striped across all disks
	- Round robin striping
- RAID 1
	- Mirrored disks
	- Data is striped across disks
	- 2 copies of each stripe on separate disks
	- Read from either but write to both
	- Recovery is simple
	- Expensive
- RAID 5
	- Parity striped across all disks
	- Round robin allocation for parity stripe
	- Commonly used in network servers
	- Size is (N-1)\*SizeOfDisk

#### Rebuilding
- When a drive fails - the system has to rebuild
- This can take a long time
- System can still perform ok
- Hot-swap drives mean no downtime
- Or a 'hot spare' drive is always in system for automatic rebuilds. 