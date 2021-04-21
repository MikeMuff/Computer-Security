## Final Lab

- Michael Muffoletto (q91w347)
- CSCI 476/594
- muffmike1@gmail.com
- 4/20/21

# Statement of Academic Honesty
I Michael Muffoletto (q91w347) agree that the solutions presented below are entirely my own. If I have used resources that are not my own, I have included appropriate citations.

# Task 1.1
System() is considered to be unsafe while execve() is considered to be safe is due to a few reasons. While both of these commands can be used to execute external programs, the implementaion of system() compared to execve() is considered unsafe. The execve() function separates data and code while system() does not. This is because system() has a command parameter and a data parameter while execve() does not. A single string can be passed in and any valid command will be executed. This allows the user of a program to append any valid command to their input and have it executed at the privlidge of the program. Execve() requires that the environment variables are specified for the child process while system() inherits all environment variables from the parent process.  

# Task 1.2
For the shellshock vulnerability to be exploitable, the two conditions that need to be satisfied are the server must be using bash and the attacker has to be able to send environment variables to the server.   

# Task 1.3
Firstly, the nc -l 707 command tells machine 1 to listen for a connenction to be made on port 7070. Then machine 2 forms that conection with the command /bin/cat < /dev/tcp/10.0.2.6/7070 >&0. Afterwards the input and output are changed. /dev/tcp/10.0.2.6/7070 tells machine 2 to listen for input from port 7070 on machine 1 by the command >&0. After the connection is astablished input typed into Machine 2 will be printed back to machine 1.

# Task 1.4
ASLR stands for Address Space Layout Randomization. How this process works is by starting the stack frame of a program at different laces in memory. This makes the buffer-overflow more difficult because the memory address that the overflow tells the program to return to might not even be in the valid address space of the program, causing a segmentation fault. This means the attacker will repeat their attack until successfull.

# Task 1.5
The underlying cause for XSS vulnerabilites is code that includes unvalidated data in an HTTP response.   

# Task 1.6
Reflected XSS exploits occurs when an attacker causes a user to supply dangerous content to a vulnerable web application, which is then reflected back to the user and executed via web browser. Stored XSS exploits occur when an attacker injects dangerous content into a data strore that is later read and included in dynamic content.   

(Task 1.5 and 1.6 refrence: https://owasp.org/www-community/attacks/xss/#:~:text=As%20the%20examples%20demonstrate%2C%20XSS,data%20in%20an%20HTTP%20response.&text=Reflected%20XSS%20exploits%20occur%20when,executed%20by%20the%20web%20browser. )   

# Task 1.7

# Task 2.1
