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
