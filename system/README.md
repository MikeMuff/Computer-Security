# Systems & Software - Towards Security
# Michael Muffoletto (q91w347)
# muffmike1@gmail.com
# CSCI 476
# 1/28/21

## Task 1
fork() = System call used to create a new process by duplicating the calling process and making it a child of the call.
exec() = System call used to create a new process by replacing the calling process with a new process image.

## Task 2
![ProgramInMemory](https://user-images.githubusercontent.com/33213355/106515903-8ccac080-6493-11eb-8809-a13a640298fd.jpg)
- Kernal Space: User code cannot be write to these addresses, doing so results in a Segmentation Fault. 
- Stack: Grows down
- Memory Mapping Segment: File mappings ( includeing dynamic libraries) and anonymous mappings. Example: /lib/libc.so
- Heap: Grows up
- BSS segment: Uninitialized variables, filled with zeros. Example: staic char *userName;
- Data segment: Static variables initialized by the programmer. Example: static char *gonzo = "God's own prototype";
- Text segment (ELF): Stores the binary image of the process (e.g., /bin/gonzo)

## Task 3
Data is the input or output of an application while code is the set of instructions that specify what to do with the input. The main difference between these two variables is that data is malleable, it can change while code defines behavior of the data. This means that data and code are not mutually exclusive and must have a distinction between the two.


## Task 4
Spyware, people accessing your network, files, etc remotely, using your computer for malicious intent, recruited to botnet.

## Task 5
Trust boundary: A location on the data flow diagram where data changes its level of trust. Any place where data is passed between two processes.

## Task 6
Function arguments, return address, previous frame pointer, local variables.
## Task 7
main = 0x55a47dccf249
printf = 0x7f8278032e10
argv = 0x7ffc6c8cc733
environ = 0x7ffc6c8cb1b8

## Task 8
Preprocessing: Obeys commands that begin with #.
Compiling: Takes the output of the prepocessor and generates assembly langauge.
Assembly: The assembler will convert the assembly code into pure binary or machine code.
Linking: The linker merges all the object code from multiple mudules into a single one.
