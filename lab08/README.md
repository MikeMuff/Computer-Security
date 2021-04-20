## Lab08

- Michael Muffoletto (q91w347)
- CSCI 476/594
- muffmike1@gmail.com
- 4/15/21

# Task 1
In this task we are asked to dervie a public key given p, q, and e provided by Travis. The values will then be put into a C program that we are given in the lab instructions and then are slightly modified. After running the program, we are given our private key.   
<img width="744" alt="Screen Shot 2021-04-20 at 11 31 32 AM" src="https://user-images.githubusercontent.com/33213355/115439598-fe312a00-a1cb-11eb-9bc2-6557822ead23.png">   

# Task 2
In order to successfully complete this task, we first have to convert the ASCII string to a hex-encoded string, then the hex string to a BIGNUM using the BN_hex2bn() function. We are given the public key values from the lab and a private key to verify our result.   

<img width="622" alt="Screen Shot 2021-04-20 at 12 53 29 PM" src="https://user-images.githubusercontent.com/33213355/115448910-79e4a400-a1d7-11eb-9cd2-1d46a57c3ec2.png">   
<img width="593" alt="Screen Shot 2021-04-20 at 12 13 09 PM" src="https://user-images.githubusercontent.com/33213355/115444666-17d57000-a1d2-11eb-891a-17642ac0fd20.png">   

# Task 3
In order to successfully decrypt the message for this task I firstly copied my encrypt_message.c code and created a decrypt_message.c and made some changes. I used the cipher text given and declared it as value C. I then converted it with BN_hex2bn() and used the same n and d values that was given in task two. After that I changed the BN_mod_exp values around to decrypt. I lastely ran the decode python command with the decrpytion result that outputed the message "Password is dees".   
<img width="669" alt="Screen Shot 2021-04-20 at 1 03 48 PM" src="https://user-images.githubusercontent.com/33213355/115450233-e3b17d80-a1d8-11eb-950c-4cde1044a72e.png">   
<img width="733" alt="Screen Shot 2021-04-20 at 12 55 58 PM" src="https://user-images.githubusercontent.com/33213355/115450267-eb712200-a1d8-11eb-928d-bb2a948e505b.png">   
