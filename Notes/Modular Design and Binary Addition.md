# Modular Design and Binary Addition

## Truth Tables to Boolean Expressions

- Product Term: Boolean expression that ANDs multiple variables, may or may not be complemented.

1. Each row in a table has a product term associated with it. 
2. Remove product terms from rows with 0s.
3. OR the rest of the product terms

- Can use this format to create schematic diagrams. 

## Combinational Design
- Integers are often stored in state as 32-bit values.
- Can compare relative magnitude of two integers by comparing values and outputting A vs. B (2 bits).
- Instead of creating a truth table, we create 32 smaller circuits, that check one bit at a time.
- Assume that A = B, until they differ at a bit (at this point, they're unequal).

## Bases
- We've created a code that assigns arbitrary meanings to symbols.
- Can change the meaning by changing the code.
- Can implicitly find a code given context, or explicitly if its given.
- Interpretation of bits depends on the context. 
<br> 
- A base represents how many characters are in the "alphabet".
- We can traverse through the set of bases, then we add another character once we run out.
- Bases are positional (the position of a number changes the value).
- Can find the value of a number by summing each value times its weight.
<br>
- Can create a binary representation of a number by repeatedly dividing by 2 and adding remainder, then reversing it.

## Hexadecimal
- Base system, like binary or decimal.
- Each value in hex is on a scale of 1-16.

| Decimal | Binary | Hex |
| ------- | ------ | --- |
| 0       | 0000   | 0   |
| 1       | 0001   | 1   |
| 2       | 0010   | 2   |
| 3       | 0011   | 3   |
| 4       | 0100   | 4   |
| 5       | 0101   | 5   |
| 6       | 0110   | 6   |
| 7       | 0111   | 7   |
| 8       | 1000   | 8   |
| 9       | 1001   | 9   |
| 10      | 1010   | A   |
| 11      | 1011   | B   |
| 12      | 1100   | C   |
| 13      | 1101   | D   |
| 14      | 1110   | E   |
| 15      | 1111   | F   |


## Binary (Modular) Addition
- Use fixed-width binary numbers, based on our processor strength.
- Binary addition works the same as decimal addition, unless we carry. 
- This is essentially modular addition, where we have a maximum value we can reach.
- Number line shifts into a number wheel:
	- Add is a CCW shift
	- Subtraction is a CW shift
- If the result of modular addition is unequal to the result of decimal addition, then we have an OVERFLOW.

## Two's Complement Representation
- We can interpret these bits in numerous ways.
- Binary doesn't work with negative numbers, decimals, etc.
- Can represent subtraction as adding a negative number.

## Bitshifting
- Shifting left adds a 0 to the last element, and causes the most significant one to move.
- In the case of a signed number, the 1 shifts over if the first number is 1.
- In the case of an unsigned number, a 0 is added.