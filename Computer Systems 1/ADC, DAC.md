Subjects/ Topics: #Electronics #ADC #DAC

**Inputs:**
- Sounds
- Temperature
- Touch
- Motion
- Light, images
- Magnetism
- Acceleration
- etc

Many inputs will be analogue, read by a transducer or sensor. They may have digital outputs but have internal conversion to digital

**Analogue-to-Digital** converter (ADC)

![[ADC.png]]


**Temperature as an example**
- Range in UK is -20 - 35 degrees C
- Continuous - infinite precision
- Analogue input
- Convert to digital (12 bit conversions)

#### Scaling/Amplifying

- Input to ADC could be limited (e.g. to 1.8V)
- Signal may be small so an amplifier is needed
	- e.g. small signal from 0V to 1V
	- This would be read as 0 to 4096x1/1.8 = 2275
	- Each step would be 1/2275 volts

- Signal may be negative e.g. -1 to +1V
- In practice signal is shifted "up" so 0=-1V and 4096=1V

### ADC

- Can sense anything with appropriate transducer
- Design decisions
	- Number of bits?
	- Speed of conversion?
	- Cost
- All ADC use one or more comparators which compare two analogue inputs and produce a digital output depending on which input is higher
- The simplest system to understand is probably one that is not often used: the flash ADC
![[Simplified ADC.png]]

**The Flash ADC**
- Very fast but expensive
- One comparator for every quantised voltage level (8-bit ADC will contain 256 comparators, each producing a digital output)
- 256 outputs can be quickly encoded into the required 8-bit digital output

**Range and Quantisation**
- If full scale range is 3.3V then each ADC step is $\frac{3.3}{4096}=0.0008V$ or 0.8 mV
- Depends on the settings used and the ADC may use a "reference voltage"
- For AC signals (e.g. microphones) 0V will be set in the middle of the range

### DAC

- Takes a digital input and converts to an analogue voltage
- Same precision/quantisation issues as with the ADC
- Same cost/speed issues as with the ADC but always faster than a ADC except maybe the flash ADC
- Perfect reproduction of analogue signal is not normally possible

- I2C uses one wire for data and one for a clock
- Computer sends an I2C address then reads the data back

### Sampling

- Need to sample at least as fast as the Nyquist rate
- 2x highest frequency in the signal
- Otherwise you get aliasing/moire
- If you can't - you have to filter out all frequencies above sampling rate/2

### PWM
- Pulse Width Modulation
- on/off signal often used for motors or LEDs
- The more ON the brighter the LED or the faster the motor turns
- Microcontrollers usually have PWM hardware to make these signals
![[PWM.png]]

