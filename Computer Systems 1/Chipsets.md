Subjects/ Topics: #CPU #Chipsets #Motherboard

- The 'Chipset' links all the components of typical computers
- Changes every few years

- Chipset joins up the main buses in the system
![[chipset.png]]
- North is fast and South is slow
- North bridge deals with mainly RAM and CPU
- South bridge typically deals with peripherals
- PCIe eventually replaced a lot of separate buses, connected to South bridge

- **Remember** PCIe split into lanes to gain bandwidth
- Typical system uses a lot of PCIe lanes
- More advanced chipset have more lanes available
- Very useful if there are two 16 lanes GPUs or multiple 4 lane SSDs

**Old Dual CPU motherboard example**
![[chipset2.png]]
- Needs very high bandwidth to RAM from multiple CPU chips

**Server Motherboards**
![[server motherboard.png]]
- Much more RAM
- Onboard RAID
- ECC RAM (Error correcting)
- Web accessible

**UltraPath Interconnect**
- UPI
- Point to point link between CPU chips and to chipset
- Around 20Gib/s
- Handles cache coherency

**BIOS**
- Firmware is on motherboard
- Hardware initialisation/ start-up test
- Booting
- Stored in Flash (so it can be updated)
- MS-DOS used I/O functions in BIOS to help standardise PCs
- Finds a boot loader on disk/CD/USB
- Loads first sector of disk into RAM, then runs that code to boot

**UEFI**
- Replaces old BIOS
- CPU-independent: ARM/Intel
- Supports 64-bit systems
- Boot services and Runtime services
- Date, time, NVRAM
- GOP - graphics output protocol
- Does not rely on boot sector (uses NVRAM data to boot OS)

**Raspberry pi 5 chipset**
- 'RP1' handles I/O instead of the processor chip
	- Analogue things
	- Ethernet, camera/ LCD, USB GPIO
	- SPI, I2C, seral, PWM