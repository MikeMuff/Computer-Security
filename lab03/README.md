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
RA: 0xffffce88+0x90
I was able to successfully execute my attack by running the debugger of the stack-L1 file in order to find the return address as well as the offset. After obtaining this information I populated the start variable with 517 like we did in lecture, I then populated the ret variable with the return ebp address as well as the offset numerical value found while using the debugger. Below I have attached pictures of my python code and the the stack-L1 compiling.  
<img width="587" alt="Screen Shot 2021-02-28 at 3 10 23 PM" src="https://user-images.githubusercontent.com/33213355/109435609-7fdcb680-79d8-11eb-832b-458c35e6dff6.png">  
<img width="1136" alt="Screen Shot 2021-02-28 at 3 08 15 PM" src="https://user-images.githubusercontent.com/33213355/109435649-a4d12980-79d8-11eb-819c-4d184067ba8b.png">  

## Task 3
Not being able to input the offset was tricky for this task. I was able to get my exploit attack to work by "spraying" the return address over the possbile size of the buffer (100-200 bytes). Then after running this exploit I was able to get a root shell.  
<img width="649" alt="Screen Shot 2021-03-01 at 9 12 17 PM" src="https://user-images.githubusercontent.com/33213355/109596419-76844480-7ad3-11eb-8a02-f22ce8cac468.png">  
<img width="1140" alt="Screen Shot 2021-03-01 at 9 12 03 PM" src="https://user-images.githubusercontent.com/33213355/109596441-81d77000-7ad3-11eb-8fdb-d9ea1332b7f8.png">  


## Task 4.1
After executing the make setiud call, I initially ran a32.out and a64.out without adding the setuid(0) shellcode. This ultimately executed a normal seed shell for both programs that do not contain root privileges. 
<img width="1044" alt="Screen Shot 2021-03-01 at 10 08 20 AM" src="https://user-images.githubusercontent.com/33213355/109532335-3f337a80-7a76-11eb-9eed-c0650f714f46.png">  
After adding the setuid(0) shellcode to both 64 and 32 bit statements and executing the make setuid call, when I ran both a32.out and a64.out it executed a root shell for me to use.  
<img width="992" alt="Screen Shot 2021-03-01 at 10 14 09 AM" src="https://user-images.githubusercontent.com/33213355/109533053-0942c600-7a77-11eb-8bd1-c1103e0e6a97.png">  

## Task 4.2
After adding the 32bit setuid(0) shellcode to our initial exploit.py file, I was able to run the exploit on our stack-L1 file and it executed properly even in the dash shell. This gave me a useable root shell.  
<img width="498" alt="Screen Shot 2021-03-01 at 10 22 40 AM" src="https://user-images.githubusercontent.com/33213355/109534399-89b5f680-7a78-11eb-9d7b-05010c930f37.png">  
<img width="1009" alt="Screen Shot 2021-03-01 at 10 23 36 AM" src="https://user-images.githubusercontent.com/33213355/109534434-920e3180-7a78-11eb-852b-e38a3c3167a8.png">  

## Task 5.1
After enabling ASLR, I ran my intial exploit attack on the stack-L1 file and instead of executing a root shell, it gave me a segmentation fault error.  
<img width="594" alt="Screen Shot 2021-03-01 at 10 27 49 AM" src="https://user-images.githubusercontent.com/33213355/109534826-fcbf6d00-7a78-11eb-8fd4-2b415174927f.png">  

## Task 5.2
After running the brute-force attack on the stack-L1 program. It took a few minutes, but after many trial and error attempts on the return address the program finally got the correct address and gave me a root shell.  
<img width="1017" alt="Screen Shot 2021-03-01 at 10 44 08 AM" src="https://user-images.githubusercontent.com/33213355/109536898-83754980-7a7b-11eb-9841-e00ee83a609d.png">  

## Task 6.1
After compiling the stack.c file with StackGuard Protection on, instead of executing a root shell I recieved a "stack smashing detected: terminated" output.  
<img width="477" alt="Screen Shot 2021-03-01 at 10 54 39 AM" src="https://user-images.githubusercontent.com/33213355/109537954-c2f06580-7a7c-11eb-8266-1091b8185fe1.png">  

## Task 6.2
After compiling call_shellcode into a32.out and a64.out with -z noexecstack we get a segmentation fault because with the program being non executable it cannot be directly executed by the computer and is also created to perform a specific task. It is so difficult, because the attack code that is injected on the stack cannot be executed properly.  
<img width="855" alt="Screen Shot 2021-03-01 at 11 03 55 AM" src="https://user-images.githubusercontent.com/33213355/109539120-2a5ae500-7a7e-11eb-97c3-7d0f66a29ba3.png">  


