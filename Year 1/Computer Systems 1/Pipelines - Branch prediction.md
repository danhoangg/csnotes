Subject/Topics: #CPUs #pipeline

- CPUs pipeline
	- Fetch, decode, execute cycle overlap one another
- In case of a branch, pipe must be flushed as instructions being fetched and decoded are no longer valid

#### ARM pipeline

- Fetch
- Decode
- Execute

- Fetch
- Decode
- Execute
- Memory load/store
- Write (data extend)

Branches are a problem, here's how to deal with them:

### Multiple streams
- Have two pipelines
- Prefetch each branch into a separate pipeline
- Use appropriate pipeline

- Leads to bus and register contention
- Multiple branches lead to further pipelines being needed

### Prefetch branch target
- Target of branch is prefetched in addition to instructions following branch
- Keep target until branch is executed

### Loop buffer
- Very fast memory, stores last N instructions in sequence
- Maintained by fetch stage of pipeline
- Check buffer before fetching from memory
- Very good for small loops or jumps

### Branch prediction (static)
- Predict: never taken
- Assume that jump will not happen
	- Always fetch next instruction
- Predict always taken
	- Assume that jump will happen

### Branch prediction (2)
- Predict by Opcode
	- Some instructions are more likely to result in a jump than others
	- Can get up to 75% success
- Taken/Not taken switch
	- Based on previous history
	- Good for loops

**2 bit predictor**
- 2 bit code for recording branch behaviour
- Records using a state-machine
![[Branch predictor.png]]

### Branch prediction (3) *historic*
- Was used in SPARC/MIPS/PA-RISC...
- Delay slot
	- Rearrange instructions a bit
	- Run the instruction after the branch anyway