# Boolean Functions and Bitwise Operators

## Everything a Computer Can Do
A computer can do two things:
- State Storage (storing info) -> eg. pawns' positions on a game board
- State Manipulations (operations that edit states) -> eg. cards that indicate how to move the pawns

Input can go into state storage, and state storage is used to generate outputs.

State storages are defined by amount of storage, and speed of retrieval.
State manipulatons are defined by operations that can be performed (architectures).

Computers have internal clocks that run to perform operations.

## Boolean Basics
State storage contains binary (in terms of bits).

Map voltages to 0s and 1s, then perform boolean algebra.

4 different representations of a boolean relationship:
* Expressions
* Truth Tables
* Gates (Schematics)
* HDLs

### Operations
#### Not
**Expression:** $f(x)=x'$

**Truth Table:**
| x   | f(x) |
| --- | ---- |
| 0   | 1    |
| 1   | 0    |

**Schematic:**
![[Pasted image 20220117085416.png|500]]

**HDL:**  `not n1(f, x)`

#### And
**Expression:** $f(x, y) = x*y$

**Truth Table:**
| x   | y   | f(x, y) |
| --- | --- | ------- |
| 0   | 0   | 0       |
| 0   | 1   | 0       |
| 1   | 0   | 0       |
| 1   | 1   | 1       |

**Schematic:**
![[Pasted image 20220117085617.png|500]]

**HDL:** `and a2(f, x, y)`

#### Or
**Expression:** $f(x,y) = x + y$

**Truth Table:**
| x   | y   | f(x, y) |
| --- | --- | ------- |
| 0   | 0   | 0       |
| 0   | 1   | 1       |
| 1   | 0   | 1       |
| 1   | 1   | 1       |

**Schematic:**
![[Pasted image 20220117085827.png|500]]

**HDL:** `or o3(f, x, y)`

## An Introduction to Verilog
Verilog is NOT a programming language, but instead a hardware description language!

Circuits are called modules.

To create a module:
* Mark beginning and end with start and end statements.
* Name module. 
* Add wires. 
* Add gates. 

![[Pasted image 20220117090532.png|500]]

``` verilog
module test (o, x, y)
output o;
input x, y;
wire or_wire, not_wire;

or o1(or_wire, x, y);
not n1(not_wire, y);
and a1(o, or_wire, not_wire);

endmodule // test
```

## Testing Verilog
To test modules, we build another module that contains and runs our test module.

We modify our inputs (provided with `reg`), then dump outputs to a file.

We also use `monitor` to print outputs whenever a wire's value changes.



## XOR Function
**Uses for state data:**
* Data (values actually don't matter in the context of the algorithm)
* Indirection/Addressing (value matters, because it tells us where to find another value)
* Control (tell us which branch to go into)

### XOR
Returns true if an odd number of inputs is true.

Can be used as a toggle-able NOT gate.

**Expression:** $f(x) = x \oplus y$

**Truth Table:**
| x   | y   | f(x, y) |
| --- | --- | ------- |
| 0   | 0   | 0       |
| 0   | 1   | 1       |
| 1   | 0   | 1       |
| 1   | 1   | 1       |

**Schematic:**
![[Pasted image 20220117091638.png|500]]

**HDL:**
`xor x1(f, x, y)`



## Bitwise Operations
How do we manipulate individual bits before storing?

Can use hexadecimal in variable declaration to initiate char arrays (i.e. strings)


```C
unsigned char a = 0xa3; // 10100011
unsigned char b = 0x05; // 00001111

unsigned char c = ~a; // 01011100 (not function)
unsigned char d = a & b; // 00000011 (and function) -> AKA a bitmask
unsigned char e = a | b; //10101111
unsigned char f = a ^ b; //10101100
```

Note that these bitwise are different from operators (which work on holistic sets).