## Lab04

- Michael Muffoletto (q91w347)
- CSCI 476/594
- muffmike1@gmail.com
- 3/05/21

# Task 1
After booting up and accessing a shell from the mysql database I was able to access the sqllab_users database, then was able to print the contents of it using the SELECT * from credential command.  
<img width="1009" alt="Screen Shot 2021-03-09 at 1 56 35 PM" src="https://user-images.githubusercontent.com/33213355/110537312-c2407a80-80df-11eb-89d7-c65663f1b8f3.png">  

# Task 2.1
I was able to enter the "admin" account via typing in admin';# . I used ‘ terminate the current context of the mysql query, then inject additional information.  
![Screen Shot 2021-03-09 at 2 26 02 PM](https://user-images.githubusercontent.com/33213355/110540349-a2ab5100-80e3-11eb-8eca-3aa29076aecf.png)  

# Task 2.2
I was able to access the admin page by using the command curl 'www.seedlabsqlinjection.com/unsafe_home.php?username=admin%27%3B%23&password=' within my shell. I had to encode the special characters inputted into my username field with different numerical values.  
<img width="1424" alt="Screen Shot 2021-03-09 at 8 42 21 PM" src="https://user-images.githubusercontent.com/33213355/110573287-3b5bc400-8118-11eb-8e04-f91d140ec0ad.png">  

# Task 2.3
I tried to change the Salary value for user Alice by putting the following command into the username field. admin';#UPDATE credential SET Salary = '30000' WHERE Username = 'Alice'. It did not work because the prepared statement countermeasure only compiles the first statement. Values which are transmitted later using a different protocol are not compiled like the statement template. If the statement template is not derived from external input, SQL injection cannot occur.  

# Task 3.1
I was able to complete this task but putting using the UPDATE feature within php. I did this by loggin into Alice's account and inputing ',salary='40000 into the NickName box.  
![Screen Shot 2021-03-10 at 1 31 15 PM](https://user-images.githubusercontent.com/33213355/110693814-1a8d8000-81a5-11eb-8073-fd6f51db0649.png)  


# Task 3.2
I was able to complete this task by using the ',salary='1' WHERE ID=4;# command inside of ALice's Edit Profile feature. This changed Samy's salary value to 1 on the database.  
<img width="963" alt="Screen Shot 2021-03-10 at 2 11 34 PM" src="https://user-images.githubusercontent.com/33213355/110698253-a81f9e80-81aa-11eb-9191-6a91ea513281.png">  

# Task 3.3
I was able to change the password of Samy's user by putting the new password 'pass' into a SHA-1 hash calculator, then using the ',password='9d4e1e23bd5b727046a9e3b4b7db57bd8d6ee684' WHERE ID=4;# command to change Samy's password.  
![Screen Shot 2021-03-10 at 2 17 14 PM](https://user-images.githubusercontent.com/33213355/110698837-604d4700-81ab-11eb-9ff6-6b384366842f.png)  
![Screen Shot 2021-03-10 at 2 17 28 PM](https://user-images.githubusercontent.com/33213355/110698882-70652680-81ab-11eb-80a6-ed6212080311.png)  

# Task 4.1
I was able to finish this task but rewriting my unsafe.php file code to use prepared statements. I did this by following the example givin in the lab instructions. Then after I did that successfully I went into my getinfo.php file and changed some of the values to bind_'value' in order to properly sync what was being called in my other file. After successfully doing this when attempting to use a SQL Injection attack or enter in a user and password incorrectly, I am outputed a table with no values. When inputing a correct user/pass combo, I am outputed that user's correct values.  
Code for my unsafe.php file.
<img width="696" alt="Screen Shot 2021-03-10 at 7 04 46 PM" src="https://user-images.githubusercontent.com/33213355/110724683-7ff86580-81d3-11eb-8aa7-01af8486b5ab.png">  
Code for my getinfo.php file.
<img width="623" alt="Screen Shot 2021-03-10 at 7 04 11 PM" src="https://user-images.githubusercontent.com/33213355/110724648-6bb46880-81d3-11eb-8eae-1c7104c1b66d.png">  
Output when attempting SQL Injection attack.
![Screen Shot 2021-03-10 at 6 58 48 PM](https://user-images.githubusercontent.com/33213355/110724618-58090200-81d3-11eb-80fd-2d0c81abee3b.png)  
Output when correctly inputing user/pass.  
![Screen Shot 2021-03-10 at 7 01 59 PM](https://user-images.githubusercontent.com/33213355/110724720-930b3580-81d3-11eb-9e66-8c5cfbc4bec5.png)  





Alice';UPDATE credential SET Salary=82000 WHERE Name='Alice';
