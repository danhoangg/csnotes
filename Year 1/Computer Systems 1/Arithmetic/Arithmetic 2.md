Subjects/ Topics: #Binary 

Related:
- [[Arithmetic 1]]
- [[Arithmetic 3]]

### Numbers

- Unsigned integers
- Signed integers
	- [[#Sign magnitude]]
	- [[#2's complement]]
	- [[#1's complement]]
	- [[#Biased offset]]
- [[#Floating point]]

#### Unsigned
Normal binary numbers, 0 - $2^n-1$ 

### Signed
#### Sign magnitude
First bit in binary number is the sign, the rest is magnitude, 0 is positive, 1 is negative
Can store $-(2^{n-1}-1)$ - $(2^{n-1}-1)$

#### 1's complement
Invert the bits for a negative number
e.g. $0101_2$ = $5_{10}$ 
Therefore $1010_2 = -5_{10}$
Can store $-(2^{n-1}-1)$ - $(2^{n-1}-1)$

#### 2's complement
Number system defined such that X + (-X) = $2^n$
Invert the bits and add 1 for a negative number
e.g. $42_{10} = 0101010_2$ 
Therefore $-42_{10} = 1010110_2$

#### Biased offset
A fixed bias B is selected such that V+B >= 0 for all V
e.g. if B =7 then $0000_2 = 7_{10}$, $0111_2 = 0_{10}$


### Floating Point
A normalised number by the IEEE standard is done so:

Sign - Exponent - Implied 1 - Fraction Field

Binary Value | Normalised | Exponent | Adjusted (bias 127)
:--: | :--: | :--: | :--: 
1101.101 | 1.101101 | 3 | 130
0.00101 | 1.01 | -3 | 124
1.0001 | 1.0001 | 0 | 127

And so:

Binary Value | Normalised | Exponent | Adjusted (bias 127) | Sign, Exponent, Fraction FIeld
:--: | :--: | :--: | :--: | :--:
1101.101 | 1.101101 | 3 | 130 | 0 10000010 10110100000000000000000
-0.00101 | 1.01 | -3 | 124 | 1 01111100 01000000000000000000000
1.0001 | 1.0001 | 0 | 127 | 0 10000000 00010000000000000000000
100111 | 1.00111 | 5 | 132 | 0 10000100 00111000000000000000000



