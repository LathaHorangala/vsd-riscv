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
