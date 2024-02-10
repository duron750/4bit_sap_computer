# 4bit_sap_computer

Very simple 4 bit computer created in LogicSim 3.8.
It is based on Ben Eater's Youtube videos and Digital Computer Electronics book by Albert Paul Malvino.

The processor has a 4 bit databus and 8-bit address bus. It has 2 registers (accumulator and B register) and 2 other registers which cannot be used directly (H and L register). H and L registers are used only to address the memory.

The instruction set is limited to Load A, Load B registers, add and substract, output and halt.
TBD: implement JMP instructions.

The instruction set is loaded in ROM memory. All the logic behind it is found in excel file.

Enjoy!
