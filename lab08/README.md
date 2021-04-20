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

<img width="620" alt="Screen Shot 2021-04-20 at 12 07 37 PM" src="https://user-images.githubusercontent.com/33213355/115444598-00968280-a1d2-11eb-87b3-d7067d0e2df2.png">
<img width="593" alt="Screen Shot 2021-04-20 at 12 13 09 PM" src="https://user-images.githubusercontent.com/33213355/115444666-17d57000-a1d2-11eb-891a-17642ac0fd20.png">   

