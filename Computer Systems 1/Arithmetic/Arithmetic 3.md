Related:
- [[Arithmetic 1]]
- [[Arithmetic 2]]

### Binary Multiplication
```
		0111
x       1011
-------------
        0111    (Start with 7)
       0111     (Add 7 shifted by 1 bit)
      0000      (Add nothing)
     0111       (Add 7 shifted by 3 bits)
-------------
     1001101    (Result = 77)
```

### The arithmetic logic unit

- A selectable function unit
- Usually two data inputs, of equal size, plus a function select bus
	- The coding for this bus is important to the compiler
- The ALU can usually generate a mixture of logical and arithmetic operations

### Number bases

- Also known as radix
- The number of symbols used to represent a value
![[number bases.png]]

- int a = 54;        // Initialises a to decimal 54
- int b = 0x54;    // Initialises b to hexadecimal 54 (=$84_{10}$)
- Hex digits map directly to quads of bits
	- $0110_2 = 6_{10} = 6_{16}$
	- $1010_2 = 10_{10} = A_{16}$


### SSE Streaming SIMD extensions

- SIMD - Single instruction, multiple data
- Do same thing to many bytes
- Needs special hardware and software in CPU

**SSE uses**
- Image processing
- Video processing
- Array/vector processing
- Text processing
- General speed-up - depends on application
	- Compilers can detect code which can use SSE

Can pack the 128 bits with:
- 8x16bit words for example
- SSE can do float maths
- Extra ~50 instructions for SSE operations

**SSE2**
Can pack a 256 bit word
- 16x16 bit words
- Can do float maths

- SIMD units in processors now carry out vector tasks without needing the GPU
- The compiler needs to know it is available

