# MW23xx Microcomputer Architecture Simulator

Created to be a successor to the [CARDIAC computer](https://www.cs.drexel.edu/~bls96/museum/cardiac.html), yet with
a more usable instruction set, memory size. This project serves as a middle ground between hand-writeable assembly
computers, and valid compilation targets.
The word size of the MW23xx computer is variable, defined by the values of the xx characters. For example, the 
MW2316 features a 16 bit word and instruction size. Functionality is undefined for widths below 8 bits. The address
width of the computer is 4 less bits than the word size. Thus the MW2316 has 4906 addressable memory locations, each
16 bits wide.

## Instruction Set
Instructions all start with a 4-byte opcode, and are followed by a single argument. All instructions are the same
length, fitting inside the word-size of the computer. 

- Pop(stack**) a value off the stack pointed to by arg, and store in accumulator.
Push a value onto the stack pointed to by arg.

- Push(stack**) push accumulator value onto the stack pointed to by arg. 

- Load(val*) load the accumulator with the given address

- Store(val*) store the accumulator in the given address

- Add(val*) and Sub(val*) add / subtract the value at the given address to the accumulator

- Jz(code*) and Jnz(code*) conditional (if zero, if not zero) jumps to addr.

- Jump(code*) push the return address to the last memory location, and jump.

- Halt(exit code) halt with exit code.

Functions with no analog to the CARDIAC:

- Cast(selection, width) Selects the n-th group of bits, where each group is m-bits wide. n
is chosen by selection, and m is width.

- Jumpdd(code**) jump indirectly to the value stored in the accumulator

- Deref(val**) dereference the pointer stored at the given address, and store in the accumulator

Bootstrap code:
Pop (instack)
Store (0x03)
Pop (instack)
No-op
Jump 0x00