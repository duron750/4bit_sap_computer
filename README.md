# 4bit_sap_computer

Very simple 4 bit computer created in LogicSim 3.8.
It is based on Ben Eater's Youtube videos and Digital Computer Electronics book by Albert Paul Malvino.

The processor has a 4 bit databus and 8-bit address bus. It has 2 registers (accumulator and B register) and 2 other registers which cannot be used directly (H and L register). H and L registers are used only to address the memory.

It is a complete Turing machine, including math, load and jump functions.
The complete instruction set can be found in the Excel file. There are 16 instructions in total.

The instruction set is loaded in ROM memory. The excel file contains all the operations for each instruction. It is easier to implement the instruction decoder in ROM, but it can be also done using logic gates (maybe a future project?).
For conditional jump codes, in order to save ROM, there is a separate logic that identifies the instruction and, if carry flag or zero flag are set, it latches the instruction memory pin (A8 or A9) during the execution of the jump code. At the end of the instruction, both this latch and the flags registers are resetted.

Also there is a simple RAM contents, simple_ram_example_origram.rom that can be loaded in the computer RAM to run a counter up to F then down to 0 and again. This uses add, sub , non-conditional jump, jump if carry is set, jump if zero set.

Enjoy!
