# Decoders, Registers, and Register Files

## Decoders
- Receive encoded data (assembly/binary), then creates a set of control signals.
- Physical memory is stored as an array, with each address in binary pointing to a location.
- **Binary Decoder**: Converts a binary number into N control signals. Returns the binary number associated with a integer value. 
- Can also add in an enable signal, which can turn the decoder on or off.

## Registers
- Reset signal turns the entire output to 0.
- Enable signal keeps the whole flip flop enabled, otherwise it's off.
- A register is a set of flip-flops.

## Register Files
- Memory is comparable to arrays. 
- Can read or write data given a pointer.
- We can create an array of registers, defined as a two-part number.
	- Amount of registers
	- Size of our fixed-width data. 
- Add an enabler to know when to read or write.

![[Pasted image 20220129210411.png|350]]

- Can chain decoders and registers to control multiple registers at the same time.