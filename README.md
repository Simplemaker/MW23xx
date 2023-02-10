# MW23xx Microcomputer Architecture Simulator

Created to be a successor to the [CARDIAC computer](https://www.cs.drexel.edu/~bls96/museum/cardiac.html), yet with
a more usable instruction set, memory size. This project serves as a middle ground between hand-writeable assembly
computers, and valid compilation targets.
The word size of the MW23xx computer is variable, defined by the values of the xx characters. For example, the 
MW2316 features a 16 bit word and instruction size. Functionality is undefined for widths below 8 bits.

## Instruction Set
Instructions all start with a 4-byte opcode, and are followed by a single argument. All instructions are the same
length, fitting inside the word-size of the computer. 

- Pop(stack**) a value off the stack pointed to by arg, and store in accumulator.
Push a value onto the stack pointed to by arg.

- Push(stack**) push accumulator value onto the stack pointed to by arg. 

- Load(addr) load the accumulator with the given address

- Store(addr) store the accumulator in the given address

- Add(addr) and Sub(addr) add / subtract the value at the given address to the accumulator

- Jz(addr) and Jnz(addr) conditional (if zero, if not zero) jumps to addr.

- Jump(addr) push the return address to the last memory location, and jump.

- Halt(exit code) halt with exit code.

Functions with no analog to the CARDIAC:

- Cast(width) truncate the accumulator to the given number of bits, by taking the right hand tail.

- Indjump() jump indirectly to the value stored in the accumulator

- Deref(

```0x0: 
0x1: 
0x2:
0x3:
0x4:
0x5:
0x6:
0x7:
0x8:
0x9:
0xA:
0xB:
0xC:
0xD:
0xE:
0xF: 
```