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


# Task 2.1
