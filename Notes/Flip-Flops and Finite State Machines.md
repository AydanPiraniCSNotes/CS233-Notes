# Flip-Flops and Finite State Machines

## Propagation Delay
- Real gates don't switch instantaneously.
- Propagation delay: slight latency between when the inputs and outputs change. 
![[Pasted image 20220129191335.png|500]]

### Timing Analysis
- Very complicated, for a variety of reasons:
	- 0->1 transitions are different from 1->0.
	- Delay from one input can differ from another input.
	- Fanout: More chained gates might result in a longer switch. 
	- Long wires also slow things down. 

- We use the following assumptions:
	- Delay is a constant from any input to output.
	- We'll ignore fanout and wire delay.

### Analyzing Propagation Delay of Circuits
![[Pasted image 20220129192114.png|350]]
- Need to create and use a timing diagram.
![[Pasted image 20220129192404.png|350]]
- Find the longest possible time to get from any input to output (essentially reverse Djikstra).
- Look at every path from the input, and take the longest at every arbitrary point.




## State Storage
- Primary storage device: flip flop (1 bit, can change states once per clock cycle)

### State Storage Components
- Used to store data (eg. two NOT gates)
- Can change the value of one wire to get the value of another.
![[Pasted image 20220129193032.png|300]]
- Change NOT gates to NORs, so we have two more inputs to tell the value of a state.
![[Pasted image 20220129193105.png|350]]

| S   | R   | $Q^+$     |
| --- | --- | --------- |
| 0   | 0   | Q (hold)  |
| 0   | 1   | 0 (reset) |
| 1   | 0   | 1 (set)   |
| 1   | 1   | Forbidden |

- We can also force the state and its compliment to be equal by having only one input data variable.


- Use clocks to control exactly when certain values are used (can only use when clock is 1).

## Finite State Machine
- Use current state and user input to determine the next state of the overall system.
- Can then describe output to users.

## Finite State Machine
1. Understand the specification. 
2. Build the state diagram (which states are we keeping).
3. Convert the state diagram into a next-state table.
4. Translate the next-step table into a boolean expression.
5. Translate the next-state boolean expression into a feedback circuit.
6. Translate the output boolean expression.

## Timing Diagrams for Finite State Machines
- States only change when clock goes high. 