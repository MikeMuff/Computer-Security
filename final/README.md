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
Alice now has g<sup>y</sup> mod p and x while Bob has g<sup>x</sup> mod p and y. To get the common secret, Alice can compute g<sup>y<sup>x</sup></sup> mod p and Bob can compute g<sup>x<sup>y</sup></sup> mod p. By the rules of exponents Alice and Bob will then have the same value.   

# Task 1.8
We use hybrid encryption because public key cryptography is more secure but slower, while hybrid encryption is used to speed up communication while minimally compromising security.   

# Task 1.9.1
The libraries are found using the $PATH environment variable.

# Task 1.9.2 
A potential risk of using this approach is that the shell will execute the first matching command it finds. An attacker could then change the $PATH variable to point to a different directory where some malicious code is in an executable.

# Task 1.10
Three countermeasures to buffer-overflow attacks
1. Make the stack non-executable. Doing this makes it so the input can never be interpreted as code.
2. Adress Space Layout Randomization (ASLR). This begins the stack frame at a random memory location so that an attacker cannot use a consistent memory address when performing the buffer-overflow attack.
3. Stack guard. This is a slot in the stack frame that is expected to remain unchanged throughout the course of its existence by initializing randomly with each call.


# Task 2.1

# Task 2.2 

# Task 3.1
What the program audic.c does is it takes in a file name and then makes a call to system() with /bin/cat <filename> as the argument. Assuming a regular file name, this will print the contents of the file to the console.   
  
# Task 3.2
After compiling the audit.c file, we run the program passing in the argument "a; sudo bash". This will tell the program to open the file a and then open a privliged shell. As you can see in the image below the user now has access to the root shell and can execute any command.   
<img width="405" alt="Screen Shot 2021-04-21 at 6 47 26 PM" src="https://user-images.githubusercontent.com/33213355/115639642-594d4480-a2d2-11eb-8615-347d3f242f48.png">   

# Task 3.3
For this task, the execve() function is being used instead of the system() function. This means that we as the attacker can no longer chain additional commands onto our input. After researching the /bin/more program I found out that for long enough files, there is a section where commands can be entered. As you can see bellow after running the audit2 file with our long text.txt population file, I was able to execute the !sudo bash command, granting me root access.   
<img width="393" alt="Screen Shot 2021-04-21 at 7 14 31 PM" src="https://user-images.githubusercontent.com/33213355/115641374-2ad16880-a2d6-11eb-86a0-21db0b7989a9.png">   

# Task 4.1
One method of defeating SQL injection attacks is to sanitize the input. That is it ensure special characters are interpreted as data. While this solution is able to defeat SQL injections, it does not remove the fundamental issue that data and code are not seperated Because of this an attacker might be able to pull off a SQL injection.

# Task 4.2 
A malicious emplyee could set his/her salary to a higher value by entering in the fake' 1000000)"; # command into the password field. This is performed on SQL database shown below.   
![Screen Shot 2021-04-22 at 2 34 18 PM](https://user-images.githubusercontent.com/33213355/115781606-d67ec500-a377-11eb-9635-bfb79f81cfd9.png)   

# Task 4.3
In order for an attacker to get the database to run an arbitrary command SQL statement, he could run 0'; UPDATE credential SET Salary=0 WHERE Name='test';# . Ths is entered for the eid field. Below shows the output which first searches for anyone with an eid value of 0 and then changes anyone with the username 'test' to have a salary of 0.   
![Screen Shot 2021-04-22 at 2 39 00 PM](https://user-images.githubusercontent.com/33213355/115782121-894f2300-a378-11eb-8731-d80a22ecad94.png)   




