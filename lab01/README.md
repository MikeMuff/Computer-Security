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
Ran myenv_environ and it correctly printed out the environment variables.
<img width="1425" alt="Screen Shot 2021-02-09 at 12 10 34 PM" src="https://user-images.githubusercontent.com/33213355/107414917-e5234300-6acf-11eb-9694-399fd789bc1b.png">

## Task5.2
Changed myenv_environ owner to root and made it a Set-UID program.

## Task5.3
After setting the environment variables in the child process to be inherited be the parent process, I noticed that the myenv_environ file is now highlited red. This is to state that it is now a SET-UID program.
<img width="840" alt="Screen Shot 2021-02-09 at 12 49 36 PM" src="https://user-images.githubusercontent.com/33213355/107419965-9ed0e280-6ad5-11eb-91c9-50dc2239bd58.png">

# Task6.1

# Task 7.1

<img width="1103" alt="Screen Shot 2021-02-09 at 2 35 28 PM" src="https://user-images.githubusercontent.com/33213355/107431792-2e7d8d80-6ae4-11eb-9b06-48db9319ee8e.png">

## Task7.2
- When myprog is ran as a regular program and normal user, the program is not sleeping
- When myprog is ran as a Set-UID root as a normal user, nothing is returned. Therefor sleep is called with return variable 1.
- When myprog is ran as a Set-UID root as a root user, the program is not sleeping.
- When myprog is ran as a Set-UID user1 as a user1 user, the program is not sleeping.

## Task 7.3
Depending on the permissions within the myprog file, the sleep function called in the mylib program will either be called or halted. When calling the myprog file with the various tested conditions, the only time that the sleep function was not bypassed was when I called Set_UID root myprog program as a normal user with LD_PRELOAD environment variable exported. I belive that this was caused because the child isnt able to inherit the LD_ environment variables, therefor when calling a Set-UID program with no root permissions regardless of the LD_ environment variables it will not succeed.
