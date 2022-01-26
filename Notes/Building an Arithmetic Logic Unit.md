# Building an Arithmetic Logic Unit

## Addition Circuits
- Use modular design to work with one column at once.
- Create an element with 3 inputs, and these output value + carry.
- Allows us to perform addition and subtraction.

![[Pasted image 20220121224538.png|500]]

## Multiplexers
- Has two inputs, each input has its own logical value. Based on a third input, either one of the first inputs are returned.
- Can do the same thing, but with a scaled amount of selection inputs.
- We use slash notation to indicate amount of multiplexers.

## Arithmetic Logic Unit
- Can perform bitwise and logical operations.
- 3 control bits (4 < 6 < 8).

![[Pasted image 20220121225357.png|500]]

## More Verilog Syntax
### Bus 
- Can use buses to represent a group of wires, and pass them around at the same time.
```verilog
output [3:0] c;
input [3:0] a, b;
```
### Selecting Wires From Buses
- Use bracket notation to select a subset.
```verilog
xor x1 (o[0], a[0], b[0]);
```
### Assign Command
- Use assign command to change variables.
```verilog
assign x = a[0];
```

### Constants
```verilog
size (bits) ` encoding value;
8'b11010111;
'define CONST 8'b11010111;
```
### Equality Operator
```verilog
A[1:0] == 2'b10; //Returns a single bit output (represents a circuit)
```