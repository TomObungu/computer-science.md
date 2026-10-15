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


## Memory cells 

![[Pasted image 20261015112143.png]]