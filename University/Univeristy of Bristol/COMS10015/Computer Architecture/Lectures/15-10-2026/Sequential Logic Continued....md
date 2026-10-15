An $n$-bit register has a problem in that the value of $n$ is limited by each register needing a large number of transistors. 

Furthermore, another problem is that each register is not addressable. That is there is no random access. Addresses (or indexes) allow dynamic rather than static reference. The C program below show the difference between static and dynamic reference
![[Pasted image 20261015112241.png]]

# Solution 
A memory component that contains $2^{n'}$ addressable words and each word containing $w$ bits. This memory component has connections that allow transferal of data and addresses and control signals through buses. 

![[Pasted image 20261015111229.png]]
# Implementation
Thus we need a method of forming memory cells that can form more complex memory devices. As well as that, there is variation in volatile and non-volatile memory. 

There is the variation of memory being synchronous and asynchronous. Asynchronous means that steps are synchronised by a protocol. 

Furthermore there is random access and read only access. 

## Delay lines
The early EDSAC  used tubes of mercury in which the waves propagate slowly through them. Due to the time taken for the waves to get to ond end they are either replaced or fed back. 

## Magnetic-core memory
Memory can be represented as magnetic polarisation as "rings" or "cores". The wires are thread through the cores to control them. Since the magnetic polarisation is retain, so the memory is non-volatile. 

The terminology of "core dumped" is reference to main memory being referred core memory. 

# SRAM
Static RAM is generally faster to access and easier to interface but manufacturer in lower capacities. This makes in good for things like cache. 
## DRAM
DRAM has slower access time and is harder to interface but is in greater capacity. It also less expensive.


## SRAM Memory cells 
A memory cell is composed of two NOT gates. $bl$ and $¬bl$ are the bit lines in which the state of the memory is the state of the cell. This allows  either reading or writing the internal value. However the word line control access. This transistor requires 6 transistors thus making it a 6T SRAM cell.

Passing in a value to $bl$ will read the value and output it to $wl$. Whereas $¬bl$
will overwrite the value and output to $wl$.
![[Pasted image 20261015112143.png]]
Below is the purely transistor representation of the SRAM memory cell:
![[Pasted image 20261015112610.png]]

## DRAM cells
A DRAM cell is comprised of one transistor and one capacitor. The $bl$ is the bit line showing the access of the state and the world line again shows access to the state. 
![[Pasted image 20261015112624.png]]
However  a problem with this is that the capacitor discharges and charges slowly. The capacitor discharges even when the cell is not being read. This implies a time to refresh it which introduces a delay. 

## Memory devices
Memory devices are constructed from these components
- Memory arrays of cells either with $r$ rows and $c$ columns
- A row decoder 
- A column decoder 

Furthermore additional logic is required depending on the cell type. 
- Bit line conditions to ensure bit lines are strong enough to be effective
- Sense amplifiers to ensure the output from $wl$ in the array is usable. 

## SRAM device
SRAM devices are compromised of
- Auxiliary pins for power
- A single data pin (D).
- A collection of $n'$ address pins where $A_{i}$ is the $i_{i}$ pin
- A chip select pin (CS) which enables the divces
- A output enable (OE) pin which signals the device being is read read from
- A write enable pin (WE).
## Algorithm (SRAM-Read)
1. Drive the address into chip set $A_{i}$
2. Set WE to false, OE to true and CS to true
3. The bit of data is read onto D then CS is false

## Algorithm (SRAM-Write)
1. Drive the address onto D
2. Drive the address onto A
3. Set WE to true, OE to false and CS to true. 
4. The bit of data is then written and CS Is false. 

# $n$-cell SRAM device for $2n^{'}$
![[Pasted image 20261015113912.png]]

# Designs for DRAM devices
A DRAM devices consists of 
1. Auxiliary pins for power on and off
2. A single data pin
3. A collection of $\frac{n'}{2}$ address pins (A)
4. A chip select (CS)
5. An output enable (OE)
6. A write enable (WE)
7. **A row address strobe (RAS)**
8. **A column address strobe (CAS)**

## Algorithm for (DRAM-Read)
1. Drive the row address to A
2. Set RAS to true to get the row address
3. Drive the column address to onto A
4. Set CAS to true to latch column address
5. Set WE false and OE to true and CS to true
6. 1 bit of data is read and made available on D. CS, RAS and CAS is made false

## Algorithm for (DRAM-Write)
1. Drive the data onto D
2. Drive the row address onto A
3. Set RAS to true
4. Drive the column onto A
5. Set CAS to true
6. Set WE to true, OE to true and CS to true. 
7. 1 bit of data is written and CS, RAS and CAS is made false. 

## $n$-cell DRAM for $n=2'$
![[Pasted image 20261015114633.png]]

## Memory devices
The configuration of a device is described as something like:
$$
\delta \times \omega \times \beta
$$
Where $\delta$ is the capacity measured in multiples of bits. $\omega$ describes the width of words, measured in bits and $\beta$ is number of internal logic banks. 