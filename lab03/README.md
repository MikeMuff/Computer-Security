## Lab03

- Michael Muffoletto (q91w347)
- CSCI 476/594
- muffmike1@gmail.com
- 2/21/21

## Task1.1
When running a32.out and a64.out both programs direct me into a new zsh shell.  
<img width="857" alt="Screen Shot 2021-02-23 at 12 33 51 PM" src="https://user-images.githubusercontent.com/33213355/108897921-d5c5ee80-75d3-11eb-810e-9a5597a55ff3.png">  
<img width="411" alt="Screen Shot 2021-02-23 at 1 05 04 PM" src="https://user-images.githubusercontent.com/33213355/108901171-c9439500-75d7-11eb-96b7-9f7e864a4bc0.png">  

## Task 1.2
The main function creates a new array in order to hold the binary code within the 32-bit and 64-bit shellcode. Then the function uses strcpy in order to fill the new char code with the 64 bit or 32 bit shellcode. After that code is turned into a integer and called.

## Task 2.1
The return address is 0xffffce88 and the offset is 108.  
<img width="304" alt="Screen Shot 2021-02-23 at 12 52 32 PM" src="https://user-images.githubusercontent.com/33213355/108899821-1cb4e380-75d6-11eb-97e7-34d978b3153f.png">  

## Task 2.2
RA: 0xffffce88+0x6c
I was able to successfully execute my attack by running the debugger of the stack-L1 file in order to find the return address as well as the offset. After obtaining this information I populated the start variable with 517 like we did in lecture, I then populated the ret variable with the return ebp address as well as the offset numerical value found while using the debugger. Below I have attached pictures of my python code and the the stack-L1 compiling.  
<img width="587" alt="Screen Shot 2021-02-28 at 3 10 23 PM" src="https://user-images.githubusercontent.com/33213355/109435609-7fdcb680-79d8-11eb-832b-458c35e6dff6.png">  
<img width="1136" alt="Screen Shot 2021-02-28 at 3 08 15 PM" src="https://user-images.githubusercontent.com/33213355/109435649-a4d12980-79d8-11eb-819c-4d184067ba8b.png">  

## Task 3
buffer: 168

