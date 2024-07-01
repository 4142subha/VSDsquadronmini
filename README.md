The Virtual Disk Image (VDI) file shared in the WhatsApp group must first be downloaded. A pre-configured RISC-V toolchain environment is included in this file.Setting Up the Virtual Machine to Install VirtualBox: Download and install VirtualBox from the official website if it isn't already installed. furthermore build a new virtual machine Launch VirtualBox, then select "New."Select "Linux" as the type and "Ubuntu (64-bit)" as the version when naming the virtual machine. Set aside a minimum of 20GB of hard disk space and 4GB of RAM. Include the VDI file.
Choose the freshly generated virtual machine (VM) in the VirtualBox Manager and click "Settings." Go to "Storage" and select "Add Hard Disk" under "Controller: SATA."After selecting "Existing Disk," find the VDI file you downloaded.After choosing the VDI file, press "OK." Launch the virtual machine.The pre-configured environment ought to boot up.
Open the terminal after the virtual machine has started. Revise the Package List Set up the dependencies. Create the DumpUpload object and upload it to GitHub. Set up a Git repository first. Include and Send Files Send to GitHubThese procedures will build a C program, set up the RISC-V toolchain, and produce an object dump on your virtual machine. Make sure to watch the videos for comprehensive instructions. The task can be finished by uploading the snapshots of your compiled C code and RISC-V objdump to your GitHub repository. This is an illustration of what the final photos could look like.
# Command for leafpad and evaluating c
$ cd
$ leafpad filename.c &
![VirtualBox_vsdworkshop_24_06_2024_22_50_07](https://github.com/4142subha/VSDsquadronmini/assets/173649380/7cc0c210-b6a1-40d2-af65-9afd77964e97)
# Analyzing the output by different values
$ gcc filename.c
$ ./a.out
![VirtualBox_vsdworkshop_24_06_2024_22_50_07](https://github.com/4142subha/VSDsquadronmini/assets/173649380/7cc0c210-b6a1-40d2-af65-9afd77964e97)
# Evaluating RISC-V Assembly
$ riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o filename.o filename.c
$ ls -ltr filename.o
![main](https://github.com/4142subha/VSDsquadronmini/assets/173649380/ec8f6098-f0b5-48ac-a0d4-085952557004)
# Simulating the assembly code
$ riscv64-unknown-elf-objdump -d filename.o //Gives bunch of Code
$ riscv64-unknown-elf-objdump -d filename.o | less // Gives Reduced Code
/main //to view the main function of the code
![main 2](https://github.com/4142subha/VSDsquadronmini/assets/173649380/1cbca55b-70a2-4e41-99ff-becde33fcc39)
# clock cycle divider c program
To lower the frequency of a clock signal, utilize a clock cycle divider circuit. In digital circuits, this is frequently necessary because some components have a lower clock frequency requirement than the main system clock. A basic C program that emulates a clock cycle divider is shown below. The program will generate a lower frequency output by taking the input clock frequency and dividing it by a predetermined factor.
![pro 1](https://github.com/4142subha/VSDsquadronmini/assets/173649380/17d2fa30-7dce-4b6e-8643-2fb3acf5b40f)
![pro 2](https://github.com/4142subha/VSDsquadronmini/assets/173649380/80a195c1-77ef-42ef-b43b-981dd228015c)
Function clock_signal: This one divides the frequency of an input clock signal by a specified factor and mimics the creation of a clock signal.
frequency: The clock frequency of the input, expressed in Hz.
Divide the input clock frequency by the given factor, divide_factor.
The function tracks clock cycles using a straightforward counter (clock_count), and when the counter approaches the divide factor, it toggles the output clock signal (output_clock). Based on the input frequency, nanosleep is utilized to simulate the time interval between clock pulses.
![pro3](https://github.com/4142subha/VSDsquadronmini/assets/173649380/ccadcb6f-1222-4eb5-b9ff-c6b1fb4f2fcd)
# Assembly code for the clock divider
![pro 4](https://github.com/4142subha/VSDsquadronmini/assets/173649380/a3a7c303-de6b-491c-a80f-b11c9671b034)
![pro 5](https://github.com/4142subha/VSDsquadronmini/assets/173649380/a5c5799b-046c-497b-8770-eebe609bc258)
# spike simulation for sum 1 to n
Launch a text editor, then start writing the C program.
Name the file sum_to_n.c and save it.
To access the directory containing sum_to_n.c, use a terminal.
Utilizing gcc -o sum_to_n sum_to_n.c, compile the program.
Use./sum_to_n to launch the program.
Using an Ubuntu machine and a C application, these procedures should provide you with a basic spike simulation of adding up numbers from 1 to 𝑛 n.
![spike 1](https://github.com/4142subha/VSDsquadronmini/assets/173649380/8dbba27c-6614-4edb-96a6-86d175af35b8)
$ riscv64-unknown-elf-objdump -d filename.o | less // Gives Reduced Code
![spike 2](https://github.com/4142subha/VSDsquadronmini/assets/173649380/4cea6022-118d-4620-ba1a-66981894f03a)
# Debugging code
![spike 3](https://github.com/4142subha/VSDsquadronmini/assets/173649380/ac4f391e-b0f2-47d6-8596-729078f33dbc)
#TASK 4
"Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions

ADD r6, r2, r1 SUB r7, r1, r2 AND r8, r1, r3 OR r9, r2, r5 XOR r10, r1, r4 SLT r11, r2, r4 ADDI r12, r4, 5 SW r3, r1, 2 SRL r16, r14, r2 BNE r0, r1, 20 BEQ r0, r0, 15 LW r13, r1, 2 SLL r15, r1, r2

Upload the 32-bit pattern on Github"
Here are the 32-bit instruction codes for the specified RISC-V instructions:
ADD r6, r2, r1: 0x00610133
SUB r7, r1, r2: 0x402081b3
AND r8, r1, r3: 0x00709133
OR r9, r2, r5: 0x005121b3
XOR r10, r1, r4: 0x0040a1b3
SLT r11, r2, r4: 0x004151b3
ADDI r12, r4, 5: 0x00520113
SW r3, r1, 2: 0x0020a023
SRL r16, r14, r2: 0x0020e3b3
BNE r0, r1, 20: 0x01404063
BEQ r0, r0, 15: 0x00e04063
LW r13, r1, 2: 0x00209083
SLL r15, r1, r2: 0x002091b3

Based on their encoding format, RISC-V instructions are divided into six primary types: R, I, S, B, U, and J types. Within the 32-bit instruction code, each type has a unique structure made up of fields like opcode, rd, funct3, rs1, rs2, and funct7.
![image](https://github.com/4142subha/VSDsquadronmini/assets/173649380/d1b82cc2-7ca6-46b9-a6c4-7c2375395502)

#Register-register operations are performed using the R-type.
Format: 31:25 [funct7] rs2[24:20] rs1[19:15] [14:12] funct3[11:7] rd opcode[6:0]
Add x1, x2, and x3 to 0000000 00011 00010 000 00001 0110011, for instance.

#I-type: Used for load, CSR, and instantaneous arithmetic instructions.
Imm[31:20] is the format. rs1[19:15] [14:12] funct3[11:7] rd opcode[6:0]
Addi x1, x2, 10 - 000000000010 00010 000 00001 0010011 is one example.

#S-type: Referred to in store guidelines.
Imm[31:25] is the format. rs2[24:20] rs1[19:15] funct3[14:12] imm[11:7] opcode[6:0]
SW x1, 4(x2) - 0000000 00001 00010 010 00010 0100011 is an example.

#B-type: Applied to branches with conditions.
Immediate: [31] imm[7] rs2[24:20] rs1[19:15] funct3[14:12] imm[11:8] imm[30:25] opcode[6:0]
Beq x1, x2, 8 - 0000000 00010 00001 000 00010 1100011 is an example.

#U-type: Applied to higher-level instant commands.
Format: opcode[6:0], rd[11:7], imm[31:12].
Luis X1, 0x1000 - 000000010000 00000 00001 0110111, as an example.

#J-type: Jump instructions are used with this type.
Immediate: [20] imm[10:1] imm[11] imm[19:12] opcode[6:0] rd[11:7]
Jal x1, 16 - 0000000 00001 00001 00000 1101111, as an example.

# Decoded Instruction
#1. ADD R-type (r1, r2, r3)
Opcode: 0110011
Function 3: 000
Funct7: 000000
Code of Instruction: 0000000 00011 00010 000 00001 0110011

#2. R-type SUB r3, r1, r2.
Opcode: 0110011
Function 3: 000
Function 7: 0100000
Code of Instruction: 0100000 00010 00001 000 00011 0110011

#3. AND R-type (r2, r1, r3)
Opcode: 0110011
Function 3: 111
Funct7: 000000
Code of Instruction: 000000000011 00001 111 00010 0110011

#4. OR R-type (r8, r2, r5)
Opcode: 0110011
Function 3: 110
Funct7: 000000
0000000 00101 00010 110 01000 0110011 is the instruction code.

#5. R-type XOR r8, r1, and r4
Opcode: 0110011
Function 3: 100
Funct7: 000000
Code of Instruction: 0000000 00100 00001 100 01000 0110011

#6. R-type SLT r10, r2, r4.
Opcode: 0110011
Function 3: 010
Funct7: 000000
Code of Instruction: 0000000 00100 00010 010 01010 0110011

#7. I-type (ADDI r12, r3, 5)
0010011 is the Opcode.
Function 3: 000
Code of Instruction: 000000000101 00011 000 01100 0010011

#8. S-type, r3, r1, and 4.
Opcode: 0100011
Function 3: 010
Code of Instruction: 000000000011 00001 010 00010 0100011

#9. R-type SRL r16, r11, r2
Opcode: 0110011
Function 3: 101
Funct7: 000000
0000000 00010 01011 101 10000 0110011 is the instruction code.

#10. BNE Type: B-type r0, r1, 20
Opcode: 1100011
Function 3: 001
Instruction Code: 01010 1100011 0000000 00001 00000 001

#11. BEQ r0, r0, 15 B-type
Opcode: 1100011
Function 3: 000
Code of Instruction: 00000000000000000000000 01111 1100011

#12. I-type LW r13, r11, 2
Opcode: 0000011
Function 3: 010
Instruction Code: 01011 010 01101 0000011 000000000010

#13. SLL R-type (r15, r11, r2)
Opcode: 0110011
Function 3: 001
Funct7: 000000
Instruction Code: 01011 001 01111 0110011 0000000 00010.
