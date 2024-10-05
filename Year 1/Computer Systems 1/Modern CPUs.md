Subjects/ Topics: #CPU 

### Multi-Core CPUs

- Originally multiple CPUs were put into motherboards to increase speed
- Multi-core is very efficient as the integration is all on one chip

### Improvements

**Key areas for improvement:**
- New SSE4.2 instructions
- Improved lock support
- Additional caching hierarchy
- Improved loop streaming
- Better branch prediction
- Faster virtualisation
- Simultaneous multi-threading
- Deeper buffers

**Improvements:**
- Instructions per clock cycle is a key aim
- Wider decoding
- Bigger micro-op cache
- More exec ports
- Out of order window increase
- Big load/store queues

**Loop detector improvements:**
- Looks at micro-ops
- Loops detected in the buffer to switch pipeline behaviour
- These tend to grow larger (depend on micro-op cache currently 4K)
- The other branch detecting units maintain more state

**Caches:**
- L3 isolates L1/2 core caches for efficiency
- L3 cache knows which cache lines are in L2 caches
- There is always small improvement

**Hyperthreading:**
- A core can look like two cores
- Separate threads can run
- Some benchmarks are 15-30% better
- Normal pipelines work well with one program
- Hyperthreading fills execution units with tasks from another thread as well
	- More efficient use of units
	- **Not** the same as having a second core
	- There are limited execution units
- Relies on thread-aware hardware

**Typical Power management**
- Separate microcontrollers looks after power
	- Can shut down cores completely
	- Can boost clock when needed (and when cool enough)
- L1 & L2 caches use more transistors each bit to save power

**Turbo boost:**
- Clock speed is increased in short bursts or if one core is in use (if temperature and power allows)
- Used on most CPUs

**Integrated memory controller:**
- Previously: RAM controller on motherboard chipset
- On-chip makes scalability easier as each processor chip can have its own bank of RAM
- Remote access between chips is slower

**Non Uniform Memory access (NUMA)**:
- Generic term useful to describe multiprocessor systems
- Separate blocks of RAM
- Local RAM is fast
- Remote RAM is accessible but slower
- Mechanisms include ccNUMA (cache coherency)
- Helps reduce bottlenecks
- Useful with large number of cores or clusters
- Also happens on multi-chiplet and meshed cores

**Vector Instructions (eg SSE)**:
- Vector unit has progress every few years - also provides extra instructions
	- CRC (error checking)
	- Text processing instructions (eg for XML)

### NPU Neural Processing Unit

- Newer CPUs will gain specialist units
- Neural net calculations are not exactly like graphics ops, so a matched design is faster

**Other special units:**
- Data streaming (moving data)
- Encryption/decryption
- Matrix accelerators (for machine learning etc)

**Intel "hybrid architecture"**
- Use a mix of **P**erformance and **E**fficiency cores
- Processes needing less performance can run on E cores and save power/heat
- E cores don't have big execution units or micro-op caches
- Newer generation Intel CPUs
	- Big (P) and Little (Efficiency) cores
	- DDR5 ram support
	- PCIe v5
- Intel Mobile CPUs
	- CPU compute is less important than power consumption - but onboard GPU is important

**AMD**
- AMD has competing CPUs with same ISA (Instruction Set Architecture)
- Optimisations include
	- Can beat Intel on IPC (Instructions per Clock cycle)
	- 12 memory channels on some chips
	- 128 PCIe 5.0 lanes

**Apple's ARM-based M\***
- Uses ARM's "Big-Little" architecture - used in phones/tablets previously
- Fast P cores plus power efficient E cores
- Rely on a smarter scheduler
- M1 had DRAM bonded on top of the processor chip
- M3 is 12P 4E down to 4P 4E
- 3nm process means chips can be tiny, lower power or have a lot of modules