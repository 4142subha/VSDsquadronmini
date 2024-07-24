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
# TASK 4
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

# Register-register operations are performed using the R-type.
Format: 31:25 [funct7] rs2[24:20] rs1[19:15] [14:12] funct3[11:7] rd opcode[6:0]
Add x1, x2, and x3 to 0000000 00011 00010 000 00001 0110011, for instance.

# I-type: Used for load, CSR, and instantaneous arithmetic instructions.
Imm[31:20] is the format. rs1[19:15] [14:12] funct3[11:7] rd opcode[6:0]
Addi x1, x2, 10 - 000000000010 00010 000 00001 0010011 is one example.

# S-type: Referred to in store guidelines.
Imm[31:25] is the format. rs2[24:20] rs1[19:15] funct3[14:12] imm[11:7] opcode[6:0]
SW x1, 4(x2) - 0000000 00001 00010 010 00010 0100011 is an example.

# B-type: Applied to branches with conditions.
Immediate: [31] imm[7] rs2[24:20] rs1[19:15] funct3[14:12] imm[11:8] imm[30:25] opcode[6:0]
Beq x1, x2, 8 - 0000000 00010 00001 000 00010 1100011 is an example.

# U-type: Applied to higher-level instant commands.
Format: opcode[6:0], rd[11:7], imm[31:12].
Luis X1, 0x1000 - 000000010000 00000 00001 0110111, as an example.

# J-type: Jump instructions are used with this type.
Immediate: [20] imm[10:1] imm[11] imm[19:12] opcode[6:0] rd[11:7]
Jal x1, 16 - 0000000 00001 00001 00000 1101111, as an example.

# Decoded Instruction
# ADD R-type (r1, r2, r3)
Opcode: 0110011
Function 3: 000
Funct7: 000000
Code of Instruction: 0000000 00011 00010 000 00001 0110011

# R-type SUB r3, r1, r2.
Opcode: 0110011
Function 3: 000
Function 7: 0100000
Code of Instruction: 0100000 00010 00001 000 00011 0110011

# AND R-type (r2, r1, r3)
Opcode: 0110011
Function 3: 111
Funct7: 000000
Code of Instruction: 000000000011 00001 111 00010 0110011

# OR R-type (r8, r2, r5)
Opcode: 0110011
Function 3: 110
Funct7: 000000
0000000 00101 00010 110 01000 0110011 is the instruction code.

# R-type XOR r8, r1, and r4
Opcode: 0110011
Function 3: 100
Funct7: 000000
Code of Instruction: 0000000 00100 00001 100 01000 0110011

# R-type SLT r10, r2, r4.
Opcode: 0110011
Function 3: 010
Funct7: 000000
Code of Instruction: 0000000 00100 00010 010 01010 0110011

# I-type (ADDI r12, r3, 5)
0010011 is the Opcode.
Function 3: 000
Code of Instruction: 000000000101 00011 000 01100 0010011

# S-type, r3, r1, and 4.
Opcode: 0100011
Function 3: 010
Code of Instruction: 000000000011 00001 010 00010 0100011

# R-type SRL r16, r11, r2
Opcode: 0110011
Function 3: 101
Funct7: 000000
0000000 00010 01011 101 10000 0110011 is the instruction code.

# BNE Type: B-type r0, r1, 20
Opcode: 1100011
Function 3: 001
Instruction Code: 01010 1100011 0000000 00001 00000 001

# BEQ r0, r0, 15 B-type
Opcode: 1100011
Function 3: 000
Code of Instruction: 00000000000000000000000 01111 1100011

# I-type LW r13, r11, 2
Opcode: 0000011
Function 3: 010
Instruction Code: 01011 010 01101 0000011 000000000010

# SLL R-type (r15, r11, r2)
Opcode: 0110011
Function 3: 001
Funct7: 000000
Instruction Code: 01011 001 01111 0110011 0000000 00010.

# TASK 5
Use this RISC-V Core Verilog netlist and testbench for functional simulation experiment and upload the waveforms.
# 1 CLONING THE REFERENCE REPOSITORY
$ git clone https://github.com/vinayrayapati/rv32i.git my_riscv_project
$ cd my_riscv_project 
![task 5](https://github.com/4142subha/VSDsquadronmini/assets/173649380/d3eb73d3-65b0-4e82-a0bb-f0359237e046)
# 2 SETTING UP THE SIMILATION TOOLS
$ sudo apt update
$ sudo apt install iverilog gtkwave -
![task 5](https://github.com/4142subha/VSDsquadronmini/assets/173649380/d3eb73d3-65b0-4e82-a0bb-f0359237e046)
# 3 RUN THE FUNCTIONAL SIMULATIONAL
$ nano iiitb_rv32i_tb.v 
compile and simulate:
$ iverilog -o rv32i_simulation iiitb_rv32i.v iiitb_rv32i_tb.v
$ vvp rv32i_simulation 
gtkwave window will open after commanding the below code
$ gtkwave simulation.vcd 

# OUTPUT

# ADD
![and](https://github.com/4142subha/VSDsquadronmini/assets/173649380/1d0da72f-fd7c-4ca4-bda9-517745b60cdf)
# ADDI
![addi](https://github.com/4142subha/VSDsquadronmini/assets/173649380/3d52659d-6f6c-43ba-bb37-2f9a31756b54)
# SUB
![sub](https://github.com/4142subha/VSDsquadronmini/assets/173649380/ce287616-48a1-4254-8675-bfd052947ba9)
# AND
![andd](https://github.com/4142subha/VSDsquadronmini/assets/173649380/8d0f4bdc-0c1a-4afb-9d90-684749d30079)
# OR
![or](https://github.com/4142subha/VSDsquadronmini/assets/173649380/5ee43392-c598-4f8e-b6dc-81f2709b7efe)
# XOR
![xor](https://github.com/4142subha/VSDsquadronmini/assets/173649380/949703ea-a183-4c62-8eda-502c870fed3d)
# SLT
![slt](https://github.com/4142subha/VSDsquadronmini/assets/173649380/6c9b6182-6073-4481-bec8-b1fec0394e2a)
# BEQ
![beq](https://github.com/4142subha/VSDsquadronmini/assets/173649380/7260714d-d821-4ac7-85f7-6f6b32ddaee1)

# TASK 6
# PROJECT NAME 

Clock Cycle Divider - Crafting a Digital Clock Divider Circuit 

# OVERVIEW

The "Clock Cycle Divider" project uses a RISC-V processor to design and build a digital clock divider circuit. A clock divider, which lowers a clock signal's frequency and produces lower-frequency signals from a higher-frequency input, is a crucial part of digital systems. This is crucial for applications like digital signal processing, communication systems, and microprocessors that need synchronized processes at various clock speeds. Create the Circuit for the Clock Divider: Make a digital clock divider that generates a lower-frequency output from a high-frequency clock input. Apply with a RISC-V Processor: Control the clock division logic and the circuit's overall operation by utilizing the RISC-V processor. Aim for Efficiency Optimization Make sure the clock divider performs at its best and uses the least amount of power possible.Verify Functionality: To guarantee precise and dependable operation, test the clock divider circuit under various conditions.

# COMPONENTS REQUIRED

RISC-V Processor
Clock Source (Crystal Oscillator)
Clock Divider Circuit
Power Supply
Reset Circuit
Input/Output Interfaces (GPIO)
Debugging Interface (JTAG)

# CIRCUIT CONNECTION

Attach the RISC-V CPU's power pins as well as any extra components to the positive power supply, or Vcc. Connect the GND (ground) to the ground pins of the RISC-V CPU and other parts. Connect pin Clock of the RISC-V processor to output of the crystal oscillator. For stability, make sure capacitors are grounded and decoupled correctly. The clock divider circuit can be designed using flip-flops or dedicated clock divider integrated circuits (ICs). Connect the clock source's input to the clock divider. Connect the output of the clock divider to the appropriate pins on the RISC-V CPU to enable internal clocking. A pull-up or pull-down resistor is used to connect a reset button circuit to the reset pin of a RISC-V processor.Verify that the reset signal is steady and free of bounce.Overall Goal  The GPIO pins should be connected to headers or external components in order to interface with other circuits or peripherals.GPIO pins should be configured as inputs or outputs according on what your project requires. The JTAG interface pins must be connected to a debugging tool or header in order to program and debug.Check to make sure the signals for the TDI, TDO, TCK, and TMS are linked correctly, as well as the ground and power. If your project requires communication interfaces, attach the matching pins (such as UART, I2C, or SPI) to the external devices or headers.Verify that the voltage levels and signal integrity are appropriate to guarantee reliable communication.

# SCHEMATIC DIAGRAM

+-------------------------------------------+
|            RISC-V Processor               |
|  +-------+                                |
|  | Clock |                                |
|  |Source |                                |
|  +-------+                                |
|      |                                    |
|      |                                    |
|  +-----------+                            |
|  |Clock      |                            |
|  |Divider    |                            |
|  +-----------+                            |
|      |                                    |
|      |                                    |
|     ---                                   |
|    | GND |                                |
|     ---                                   |
|      |                                    |
|  +-------+   +-------+   +-----------+    |
|  | GPIO  |   | JTAG  |   |  Power    |    |
|  |       |   |       |   |  Supply   |    |
|  +-------+   +-------+   +-----------+    |
|    |             |             |          |
+----|-------------|-------------|----------+

# PINOUT DIAGRAM

+------------------------+
| RISC-V Processor       |
|                        |
|    +-------------+     |
|    | CLK_IN      |<----|--- Clock Input
|    +-------------+     |
|    +-------------+     |
|    | CTRL        |<----|--- Control Signals (Start/Stop/Reset)
|    +-------------+     |
|    +-------------+     |
|    | CLK_OUT     |---->|--- Output Clock
|    +-------------+     |
|    +-------------+     |
|    | Vcc         |<----|--- Power Supply
|    +-------------+     |
|    +-------------+     |
|    | GND         |<----|--- Ground
|    +-------------+     |
+------------------------+

# PROGRAM

#include <stdint.h>
#include <stdbool.h>

// Define GPIO addresses and other constants as per your specific RISC-V hardware
#define GPIO_BASE_ADDRESS  0x10012000
#define GPIO_OUTPUT_ENABLE (GPIO_BASE_ADDRESS + 0x08)
#define GPIO_OUTPUT_VALUE  (GPIO_BASE_ADDRESS + 0x0C)

#define CLOCK_FREQUENCY    1000000 // 1 MHz clock
#define DIVIDE_FACTOR      1000    // Divide by 1000
#define TOGGLE_PERIOD      (CLOCK_FREQUENCY / (2 * DIVIDE_FACTOR))

// Function to initialize GPIO
void gpio_init() {
    // Enable GPIO output
    *(volatile uint32_t *)GPIO_OUTPUT_ENABLE = 0x01;
}

// Function to toggle GPIO pin
void toggle_gpio() {
    static bool state = false;
    if (state) {
        *(volatile uint32_t *)GPIO_OUTPUT_VALUE = 0x01;
    } else {
        *(volatile uint32_t *)GPIO_OUTPUT_VALUE = 0x00;
    }
    state = !state;
}

// Delay function
void delay(uint32_t cycles) {
    for (volatile uint32_t i = 0; i < cycles; i++);
}

int main() {
    gpio_init();
    
    while (1) {
        toggle_gpio();
        delay(TOGGLE_PERIOD);
    }
    
    return 0;
}

# TASK 7 
# Project Demonstration
https://drive.google.com/file/d/1xKlKF-Dl3EUIBdSHbNRfCSZ6eKbdPxN7/view?usp=drive_link
