## Lab01

- Michael Muffoletto (q91w347)
- CSCI 476/594
- muffmike1@gmail.com
- 2/05/21

## Task 1.1
Used pirntenv command to print out environment variables

## Task1.2
Used export

## Task2.1
After compiling myprintenv.c the output text file that was created held the same information as when I ran the printenv command except a couple variables such as  XDG_SESSION_ID and SSH_TTY changed.

## Task2.2
The output of myenv2 was identical to myenv1 after I commented out the child process and readded the parent process.

## Task 2.3
When I ran diff between myenv1 and myenv2 there was no difference between the two outputs.

## Task3.1
My observations were nothing was outputed.

## Task3.2
After changing the arguments of the execve call, it then printed out the same output as the last myprintenv file did.

## Task3.3
A new program gets its environment variables in this instance by copying whatever arguments are called inside of execve and placing them in the new program.

## Task4
Compiled and ran myenv_system

## Task5.1
<img width="1425" alt="Screen Shot 2021-02-09 at 12 10 34 PM" src="https://user-images.githubusercontent.com/33213355/107414917-e5234300-6acf-11eb-9694-399fd789bc1b.png">
