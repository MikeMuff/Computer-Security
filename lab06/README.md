## Lab06

- Michael Muffoletto (q91w347)
- CSCI 476/594
- muffmike1@gmail.com
- 4/02/21

# Task 1
I successfully encrypted this file in multiple different ways using -aes-128-cbc, cfb and ofb. I firstly created a plaintext.txt file and populated it with katy perry lyrics. Then I used the given command and encrypted the lyrics into cipher.bin, cipher2.bin and cipher3.bin. The only way to decrpyt these files would be to use the same cipher key with the -d command.   
<img width="1242" alt="Screen Shot 2021-04-08 at 4 49 28 PM" src="https://user-images.githubusercontent.com/33213355/114105869-d916f000-988a-11eb-9f54-0adc8ddb552b.png">   

# Task 2.1
I was able to successfully encrypt this photo by using the commands -aes-256-ecb and -aes-256-cbc from the cypher algorithims ECB and CBC. Then I ran those commands in the pic_original.bmp file which outputed the two encrypted image files pic1.bmp and pic2.bmp.   
<img width="1081" alt="Screen Shot 2021-04-08 at 5 06 03 PM" src="https://user-images.githubusercontent.com/33213355/114106770-c9001000-988c-11eb-8ebf-104b2302fcc9.png">   

After running those commands, we will now see two new bitmap files created in the our directory we are working in. However, if you try to open the files, an error will show telling that the file is in an unrecognized format. So, we need to retrieve the original 54-byte header in order to actually open the file as a bitmap. Here we use the commands given to us in the lab to copy the 54- byte header information from the original file into the encrypted files. And finally we have our encrypted photos, EBC followed by CBC.   
![Screen Shot 2021-04-08 at 5 33 00 PM](https://user-images.githubusercontent.com/33213355/114108591-9a843400-9890-11eb-97e2-cb110a1bc410.png)   
![Screen Shot 2021-04-08 at 5 33 42 PM](https://user-images.githubusercontent.com/33213355/114108612-a53ec900-9890-11eb-80e5-72215f34a330.png)   

What have learned from doing this task is that using EBC encryption is better than not using one at all, but we can still see the majority of the photo. The encryption just blurred out an extent of the picture. Using CBC was better and the optimal pick out of the two encrytpion teqniques due to the fact that the photo is completely blurred out and we cannot see anyt detaial at all of the original.   

# Task 2.2
For this task I found a picture of a penguin, then used the encryption steps in the previous task in order to encrypt the file using the CBC technique.   
![Screen Shot 2021-04-08 at 5 44 26 PM](https://user-images.githubusercontent.com/33213355/114109346-542fd480-9892-11eb-881a-b4a965594613.png)   
![Screen Shot 2021-04-08 at 5 44 36 PM](https://user-images.githubusercontent.com/33213355/114109359-598d1f00-9892-11eb-9184-64a65fc59654.png)   

# Task 3.1
I was able to successfully encrypt these files using 128-bit AES with CBC mode by using the encryption code in previous tasks, then decrypting the files using the -d with -nopad command. Then I was able to view what was added by using the xxd command on the decrypted files. I learned that padding occurs during the ECB encryption.   
<img width="1261" alt="Screen Shot 2021-04-08 at 6 22 29 PM" src="https://user-images.githubusercontent.com/33213355/114111724-ee464b80-9897-11eb-8951-adfc6d0787b4.png">   

# Task 3.2
I learned with research that CFB and OFB techniques do not require padding because they take the outputs of the previous block which has to be the same size as the cipher block size. This has to be the same size as the inputs of its last cipher block encryption.   

ECB   
<img width="1091" alt="Screen Shot 2021-04-08 at 6 36 15 PM" src="https://user-images.githubusercontent.com/33213355/114112336-68c39b00-9899-11eb-89be-a6860eb34588.png">   

CFB   
<img width="562" alt="Screen Shot 2021-04-08 at 6 38 35 PM" src="https://user-images.githubusercontent.com/33213355/114112442-a7595580-9899-11eb-9f7a-e1b325a48cc4.png">   

OFB   
<img width="1130" alt="Screen Shot 2021-04-08 at 6 39 49 PM" src="https://user-images.githubusercontent.com/33213355/114112541-d2dc4000-9899-11eb-9e34-00a22eed5f83.png">   

# Task 4.1
- In ECB mode, only one block is affected when any problem in a cipher text happens; furthermore; moreover, each block is decrypted independently. However, the corrupted bit of the 55th byte in cipher text block 8 bytes might spread to all n bits in plaintext block 8 bytes since we do the decryption one block at a time.
- In CBC mode, there was affect in two blocks.
- In CFB mode, there is problem in n / r number of blocks. Therefore, the error propagation criterion is poorer (Modes of Operation of Block Ciphers).
- In OFB mode, the feedback is only in the key-generation system. If the single digit of the 55th byte corrupted, then in plain text that only that byte or character is corrupted. Thus, only OFB mode shows the most promising result and almost all the texts are recovered.

# Task 4.2
After successfully encrypting, intentionally corrupting the fule and decrypting it I could only recover a few of the first words from the file with ECB.   
<img width="1416" alt="Screen Shot 2021-04-08 at 7 18 49 PM" src="https://user-images.githubusercontent.com/33213355/114115130-81cf4a80-989f-11eb-90a2-fac2eaa73c09.png">   

# Task 4.3
With CBC I was only able to once again make out a few words after decrypting the corrupted file.   
<img width="712" alt="Screen Shot 2021-04-08 at 7 24 54 PM" src="https://user-images.githubusercontent.com/33213355/114115520-34071200-98a0-11eb-8eaf-959db93f6958.png">   

# Task 4.4
With CFB I was able to decrypt more words than the other two previous techniques.   
<img width="1426" alt="Screen Shot 2021-04-08 at 7 28 19 PM" src="https://user-images.githubusercontent.com/33213355/114115761-a841b580-98a0-11eb-8b6b-2b3dbf0c1e84.png">   

# Task 4.5
With OFB the whole file was successfully decrypted except for the bit that I changed.   
<img width="1407" alt="Screen Shot 2021-04-08 at 7 33 51 PM" src="https://user-images.githubusercontent.com/33213355/114116164-67966c00-98a1-11eb-8cad-59da17987c3e.png">   

# Task 5.1   
For this task I begin by checking the uniqueness of the IV importance. If I use the same key for many things, you will be able to crack into many things that the user may have encrypted with the same code. My observation Is that the encoding with a different encryption IV will change the look of the file within.
<img width="1425" alt="Screen Shot 2021-04-08 at 7 42 39 PM" src="https://user-images.githubusercontent.com/33213355/114116852-a842b500-98a2-11eb-9f2f-f224cd96af2f.png">   

