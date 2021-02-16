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

