## Lab02

- Michael Muffoletto (q91w347)
- CSCI 476/594
- muffmike1@gmail.com
- 2/11/21

## Task1
For the first experiment, I created foo within the bash shell and when switching to bash_shellshock the trailing command of foo was executed.  
<img width="585" alt="Screen Shot 2021-02-15 at 2 56 01 PM" src="https://user-images.githubusercontent.com/33213355/107996870-a9d8b680-6f9e-11eb-9d83-b2752f7cd6b6.png">  
For the second experiment, I created foo within the bash_shellshock shell and when switching to bash the trailling command of foo was not executed.  
<img width="537" alt="Screen Shot 2021-02-15 at 2 59 26 PM" src="https://user-images.githubusercontent.com/33213355/107996907-c83eb200-6f9e-11eb-9730-6ba8dfa6e384.png">

## Task 2.1
There a alot of things that the HTTP HEADER Live extension doesnt show compared to our EV print program. For example it doesnt show server information such as  the address, port, server admin and many more.  
![Screen Shot 2021-02-15 at 3 26 14 PM](https://user-images.githubusercontent.com/33213355/107998356-38026c00-6fa2-11eb-9430-dd4dc03467f8.png)

## Task 2.2
Using the -v command makes the displayed information print out more verbose. This means that it shows additional information to the user such as ip, port, server, date and more information ontop of the Enironment Variables and shows what curl is getting as a request.  
<img width="852" alt="Screen Shot 2021-02-15 at 3 38 39 PM" src="https://user-images.githubusercontent.com/33213355/107999326-61bc9280-6fa4-11eb-8daf-3e46ba8d7430.png">

## Task 2.3
Using the -A command allowed me to set the User-Agent field to whatever string I desire, then prints out the -v extension as well.  
<img width="852" alt="Screen Shot 2021-02-15 at 3 52 39 PM" src="https://user-images.githubusercontent.com/33213355/108000239-b3feb300-6fa6-11eb-8213-ce55bd6081d6.png">

## Task 2.4
Using the -e command allowed me to set the "Referer" name to a string. This sends the "Referer Page" information to the HTTP server.  
<img width="948" alt="Screen Shot 2021-02-15 at 4 03 39 PM" src="https://user-images.githubusercontent.com/33213355/108000533-68003e00-6fa7-11eb-9449-00a762816cd1.png">

## Task 2.5
Using the -H command allowed me to change the header to a string. This creates an extra header to use when getting a web page.  
<img width="818" alt="Screen Shot 2021-02-15 at 4 05 47 PM" src="https://user-images.githubusercontent.com/33213355/108000648-b01f6080-6fa7-11eb-9829-4b53aecf5752.png">

## Task 2.2.5
curl -A, -e and -H all could be used to inject data into environment variables of the target CGI program.

## Task 3.1
Within this task I used curl -e. I was able to get the /etc/passwd file to print while creating a test string, establishing the Content-type and finally was able to get the passwd file to output by calling /bin/cat into /etc/passwd in my trailing command.  
<img width="1378" alt="Screen Shot 2021-02-15 at 5 43 34 PM" src="https://user-images.githubusercontent.com/33213355/108005226-63428680-6fb5-11eb-8f73-3ba0f10d29af.png">


## Task 3.2
I was able to get the server to tell me its process' user ID by using curl -A. I first created a test string within the initial echo command, from there I established the Content-Type and was able to get the user ID to output by calling /bin/id in my trailing command.  
<img width="1261" alt="Screen Shot 2021-02-15 at 4 57 46 PM" src="https://user-images.githubusercontent.com/33213355/108003271-7c483900-6faf-11eb-92b7-b88365c39856.png">

## Task 3.3
I was able to create a file inside the /tmp folder by using curl -e. I first created a test string within the initial echo command, from there I established the Content-Type and was able to get the server to create a file within the temp folder but running /bin/mktemp in my tralling command.  
<img width="1271" alt="Screen Shot 2021-02-16 at 9 47 43 AM" src="https://user-images.githubusercontent.com/33213355/108094982-9bd97300-703c-11eb-8e06-25fa5c3b1642.png">  
Here is the /tmp folder within my shellshock bash that was created  
<img width="750" alt="Screen Shot 2021-02-16 at 9 48 19 AM" src="https://user-images.githubusercontent.com/33213355/108095102-bf042280-703c-11eb-93db-617f4ba58227.png">  

## Task 3.4
I was able to delete the file inside the /tmp folder by using curl -A. I first created a test string within the initial echo command, then established the Content-Type and was able to remove the file by using /bin/rm /tmp/tmp.G4rJsRQrY0 which deleted the file.  
<img width="1372" alt="Screen Shot 2021-02-16 at 10 04 13 AM" src="https://user-images.githubusercontent.com/33213355/108096807-a137bd00-703e-11eb-9fb5-e0d0703403c5.png">  
Here is the /tmp directory after calling the command above.  
<img width="877" alt="Screen Shot 2021-02-16 at 10 04 47 AM" src="https://user-images.githubusercontent.com/33213355/108096883-b44a8d00-703e-11eb-8026-f65361b0374d.png">  

## Task 3.5
I intially tried to print the contents of the /etc/shadow file with my similar tactic that I ran within Task 3.1 while using the cat command but that did not work. I realized after some tinkering that my initial attempt did not work because I did have permission to view this file and needed to run sudo before cat in order to view the shadow file. This was unsuccessful because sudo is normally stored within the /usr/bin/sudo, after using the whereis command I realized that sudo was not an option within the web server making my attempt non-accessible.  

## Task 4
I was able to eastablish connection from my attacker shell to the online web server. I have posted pictures bellow of both shells.  
Attacker shell.  
<img width="881" alt="Screen Shot 2021-02-16 at 11 39 53 AM" src="https://user-images.githubusercontent.com/33213355/108106975-dc8cb880-704b-11eb-937d-7c9ec4faba05.png">  
Server shell.  
<img width="1279" alt="Screen Shot 2021-02-16 at 11 40 11 AM" src="https://user-images.githubusercontent.com/33213355/108107083-fd550e00-704b-11eb-8321-8f44c366af1d.png">  

## Task 5
For this task I nagivated into the vul.cgi file with the command nano /usr/lib/cgi-bin/vul.cgi and edited the script to /bin/bash.  

## Task 5.1
After reruning the same attack that I previously did for 3.1, instead of outputing the etc/passwd file it just printed "Hello World"  
<img width="1337" alt="Screen Shot 2021-02-16 at 11 58 44 AM" src="https://user-images.githubusercontent.com/33213355/108108862-6a69a300-704e-11eb-8ab7-2ff96243a9b8.png">  

## Task 5.2
Same result as the previous task.  
<img width="1264" alt="Screen Shot 2021-02-16 at 12 00 37 PM" src="https://user-images.githubusercontent.com/33213355/108109052-a69d0380-704e-11eb-8025-651cc0a3ecfc.png">  

## Task 5.3
Same result as the previous task. When nagivating to the tmp folder on the web server shell there was no tmp file created.  
<img width="1303" alt="Screen Shot 2021-02-16 at 12 03 22 PM" src="https://user-images.githubusercontent.com/33213355/108109366-fda2d880-704e-11eb-935b-0fbb0b51fba5.png">  

## Task 5.4
There was no tmp file to be deleted but I ran the rm command anyway and it still outputed "Hello World".

## Task 5.5
Same output as the previous tasks.  
<img width="1324" alt="Screen Shot 2021-02-16 at 12 05 46 PM" src="https://user-images.githubusercontent.com/33213355/108109610-5c685200-704f-11eb-87e0-0490be5c5a78.png">
