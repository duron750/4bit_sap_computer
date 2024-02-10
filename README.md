# 4bit_sap_computer


4 bit computer Simple As Possible, created in LogicSim 3.8.
It is based on Ben Eater's Youtube videos and Digital Computer Electronics book by Albert Paul Malvino.

The processor has a 4 bit databus and 8-bit address bus. It has 2 registers (accumulator and B register) and 2 other registers which cannot be used directly (H and L register). H and L registers are used only to address the memory. The procesor has a big endian architecture, however this can be easily changed by reversing H and L registers. I choosed big endian because it's easier to understand and use. 

It is a complete Turing machine, including math, load and jump functions.
The complete instruction set can be found in the Excel file. There are 16 instructions in total. 

INSTR	        HEX
NOP	          0x0 - no instruction
LDA (ADDRESS)	0X2 - loads the value from [address] in accumulator. Operand is 2 4bit values, representing the address (big endian)
LDA (VALUE)	  0x3 - loads immediate the [value] in accumulator. Operand is 1 4bit value
LDB (ADDRESS)	0x4 - loads the value from [address] in B register. Operand is 2 4bit values, representing the address (big endian)
LDB (vALUE)	  0x5 - loads immediate the [value] in B register. Operand is 1 4bit value
ADD (ADDRESS)	0x6 - adds the value from [address] with accumulator and saves result in accumulator. Operand is 2 4bit values, representing the address (big endian)
ADD (VALUE)	  0x7 - adds [value] to accumulator and update the result in accumulator. Operand is 1 4bit value.
SUB (ADDRESS)	0x8 - extracts the value from [address] from accumulator and saves result in accumulator. Operand is 2 4bit values, representing the address (big endian)
SUB (VALUE)	  0x9 - extracts [value] from accumulator and update the result in accumulator. Operand is 1 4bit value.
STA (ADDRESS)	0xA - stores accumulator value in memmory at [address]. Operand is 2 4bit values, representing the address (big endian)
JMP (ADDRESS)	0XB - non-conditional jump to address [address]. Operand is 2 4bit values, representing the address (big endian)
JC (ADDRESS)	0xC - jump if carry bit set to [address]. Operand is 2 4bit values, representing the address (big endian)
JZ (ADDRESS)	0XD - jumo if zero bit set to [address]. Operand is 2 4bit values, representing the address (big endian)
HLT	          0xE - halts the clock
OUT	          0xF - output the contents of accumulator (in schematic there is a hex 7-seg display and LED's at output).


The instruction set is loaded in ROM memory (part of the instruction decoder circuit). The excel file contains all the operations for each instruction. It is easier to implement the instruction decoder in ROM, but it can be also done using logic gates (maybe a future project?).
For conditional jump codes, in order to save ROM, there is a separate logic that identifies the instruction and, if carry flag or zero flag are set, it latches the instruction memory pin (A8 or A9) during the execution of the jump code. At the end of the instruction, both this latch and the flags registers are resetted.

Also there is a simple RAM contents, simple_ram_example_origram.rom that can be loaded in the computer RAM to run a counter up to F then down to 0 and again. This uses add, sub , non-conditional jump, jump if carry is set, jump if zero set.

Enjoy!
