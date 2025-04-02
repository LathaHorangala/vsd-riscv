# vsd-riscv
VSDSquadron RISC-V  Mini Research internship
# Baic Details
Name:Latha H

Email:lathahorangala@gmail.com

 # Task1
* Installed virtual box and opened VDI file.
* Executed a C program to calculate the sum of n numbers and verified the output. Additionally, executed the equivalent RISC-V assembly code and validated the results.
 # Task2
* Executed a C program to calculate the factorial of entered number and verified the output. 
* Observed O1 and Ofast optimization for RISC-V object dump.
* Generated RISC-V SPIKE and observed how the registers and stack pointer updates according to the main program.
*
# Task3
# RISC-V Instruction Types 
# R-Type (Register-Register Instructions)
R-Type instructions perform arithmetic and logical operations using only registers. These instructions take two source registers as input and store the result in a destination register. They do not use immediate values or memory addresses. Examples include add, sub, and mul, which operate directly on register values.

# I-Type (Immediate & Load Instructions)
I-Type instructions involve operations that use an immediate value or perform memory loads. These instructions take a source register and a 12-bit immediate value, process them, and store the result in a destination register. Common examples include addi, which adds an immediate value to a register, and lw, which loads a word from memory into a register.

# S-Type (Store Instructions)
S-Type instructions store data from a register into memory at an address calculated using a base register and an immediate offset. The immediate value is split into two parts within the instruction encoding. Examples include sw, which stores a word from a register into memory, and sb, which stores a byte.

# B-Type (Branch Instructions)
B-Type instructions are used for conditional branching, meaning they allow the program to jump to a different instruction based on a condition. These instructions compare two registers and, if the condition is met, jump to a target address computed using an immediate value. Examples include beq, which jumps if two registers are equal, and bne, which jumps if they are not equal.

# U-Type (Upper Immediate Instructions)
U-Type instructions are used for handling large immediate values, which are stored in the upper 20 bits of a register. These instructions are mainly used for loading large constants into a register (lui) or computing addresses relative to the program counter (auipc). This helps in setting up addresses for memory access or jump operations.

# J-Type (Jump Instructions)
J-Type instructions perform unconditional jumps to a specified address while storing the return address in a register. These instructions use a 20-bit immediate value, which allows for long-range jumps within a program. The primary example is jal, which jumps to a target location and saves the return address for function calls.


![Screenshot (145)](https://github.com/user-attachments/assets/205de7d2-c7d7-4b91-89dc-6cc1f30cb180)

# lui a0,0x2b
* U-Type instuction
* Opcode(0-6):0110111
* rd(7-11):a0 equivalent to x10 register i.e.,01010
* Immediate(12-31):imm[31:12] i.e.,00000000000000000000
* 32-bit instruction:00000000000000000000_01010_0110111

# addi sp,sp,-48
* I-Type instuction
* Opcode(0-6):0010011
* rd(7-11):sp=x2 i.e.,00010
* funct3(12-14):0x0 i.e.,000
* rs1(15-19):sp=x2 i.e.,00010
* Immediate(20-31):imm[11:0] i.e.,111111010000
* 32-bit instuction:111111010000_00010_000_00010_0010011

# sd ra,40(sp)
* S-Type instuction
* Opcode(0-6):0100011
* Immediate(7-11):imm[4:0] i.e.,01000
* funct3(12-14):0x3 i.e.,011
* rs1(15-19):sp=x2 i.e.,00010
* rs2(20-24):ra=x1 i.e.,00001
* Immediate(25-31):imm[11:5] i.e.,0000001
* 32-bit instuction:0000001_00001_00010_011_01000_0100011

# jal ra,10494
* J-Type instuction
* Opcode(0-6):1101111
* rd(7-11):ra=x1 i.e.,00001
* Immediate(12-31):imm[20|10:1|11|19:12] i.e.,00001111111100000010
* 32-bit instuction:0000001_00001_00010_011_01000_0100011

