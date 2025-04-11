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
* 32-bit instuction:00001111111100000010_00001_1101111

# lw s2,12(sp)
* I-Type instuction
* Opcode(0-6):0000011
* rd(7-11):s2=x18 i.e.,10010
* funct3(12-14):0x2 i.e.,010
* rs1(15-19):sp=x2 i.e.,00010
* Immediate(20-31):imm[11:0] i.e.,000000001100
* 32-bit instuction:000000001100_00010_010_10010_0000011

# bge a5,s2,1013c
* B-Type instuction
* Opcode(0-6):1100011
* Immediate(7-11):imm[4:1|11] i.e.,11100
* funct3(12-14):0x5 i.e.,101
* rs1(15-19):a5=x15 i.e.,01111
* rs2(20-24):s2=x18 i.e.,10010
* Immediate(25-31):imm[12|10:5] i.e.,0001001
* 32-bit instuction:0001001_10010_01111_101_11100_1100011

# bne s0,s1,100f8
* B-Type instuction
* Opcode(0-6):1100011
* Immediate(7-11):imm[4:1|11] i.e.,11000
* funct3(12-14):0x1 i.e.,001
* rs1(15-19):s0=x8 i.e.,01000
* rs2(20-24):s1=x9 i.e.,01001
* Immediate(25-31):imm[12|10:5] i.e.,0000111
* 32-bit instuction:0000111_01001_01000_001_11000_1100011

 # Task4
 # Functional Simulation of RISC-V Core
  * Objective: Perform a functional simulation of the given RISC-V Core Verilog netlist and testbench.
![Screenshot (160)](https://github.com/user-attachments/assets/081f90f7-c885-4c46-ae3a-b51fce14917b)
# 1. add r6,r1,r2
![Screenshot (146)](https://github.com/user-attachments/assets/87e32f62-4a6e-4da4-902d-317a3b76705a)
# 2. sub r7,r1,r2
![Screenshot (147)](https://github.com/user-attachments/assets/c1319964-a0f7-4338-82fd-82bec48fa983)
# 3. and r8,r1,r3
![Screenshot (148)](https://github.com/user-attachments/assets/3fcddf8a-3e66-413c-b2b2-525cb0052dec)
# 4. or r9,r2,r5
![Screenshot (149)](https://github.com/user-attachments/assets/31c5e4a1-1bf8-4bcb-9a41-1f3fba11d4f6)
# 5. xor r10,r1,r4
![Screenshot (150)](https://github.com/user-attachments/assets/21fe030b-a759-40ab-8cc6-a0967c85c029)
# 6. slt r11,r2,r4
![Screenshot (151)](https://github.com/user-attachments/assets/58abf3b6-dc2e-416e-babb-496bb6faa1d1)
# 7. addi r12,r4,5
![Screenshot (167)](https://github.com/user-attachments/assets/746b7f13-aa38-4c99-a6b8-50bf8212c736)
# 8. sw r3,r1,2
![Screenshot (163)](https://github.com/user-attachments/assets/18b0c04e-6530-4938-9e62-603668003ea7)
# 9. lw r13,r1,2
![Screenshot (164)](https://github.com/user-attachments/assets/8e035440-29c4-40ce-b04d-9af950a21ed7)
# 10. beq r0,r0,15
![Screenshot (165)](https://github.com/user-attachments/assets/f73405e5-c1f3-405d-bb27-829ba60ef9d7)
# 11. add r14,r2,r2
![Screenshot (166)](https://github.com/user-attachments/assets/d7a4be99-06e6-4e83-ad71-0252b2b9adaa)

# Task5
# Application Project
# Project Name: Digital Number Display Using VSD Squadron Mini and 7-Segment Display
# Overview
This project demonstrates how to interface a VSD Squadron Mini microcontroller board with a 7-segment display to show numbers from 0 to 9. It helps in understanding digital output control and display driving, which can be further extended for timers, counters, or digital meters.
# Components Required:
* VSD Squadron Mini (Microcontroller Board)
* 1 x 7-Segment Display (Common Cathode or Anode)
* 220Ω Resistors (7x for each segment)
* Breadboard
* Jumper Wires
* USB Cable (for power/programming)
# Pin out diagram:
![Pin out](https://github.com/user-attachments/assets/f96cfbe0-55b7-4db6-b76f-2f0f9d391d6e)
# Circuit Connection
![Circuit](https://github.com/user-attachments/assets/c3512706-c6da-47b9-b0a2-5c221bb2e123)
# Pin Details:
![Screenshot (173)](https://github.com/user-attachments/assets/42bd3691-dffa-4431-8b14-985b40eb76f7)








