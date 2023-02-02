# CPU Emulator in Rust

Emulates a CHIP-8 using a variety of opcodes, 16 registers, and stack implementation for function calls and returns.

## Opcodes

* 0x0000 return

* 0x00E0 none

* 0x00EE return from subroutine

* 0x1000..0x1FFF jump to address (address is the last 3 values)

* 0x2000..0x2FFF call at this address (address is the last 3 values)

* 0x3000..0x3FFF continue if equal

* 0x4000..0x4FFF continue if not equal

* 0x5000..=0x5FFF continue if equal

* 0x6000..=0x6FFF insert kk into register x

* 0x7000..=0x7FFF add and put in x

* 0x8000..=0x8FFF => bitwise ops
                        0 => not
                        1 => or
                        2 => and
                        3 => xor
                        4 => add
                        5 => nand
                        
## Concept

The idea behind these opcodes is to give an instruction to the CPU which then gets interpreted and an action is performed. For keeping track of function calls and returns a stack is updated so that reversing through memory is possible.
