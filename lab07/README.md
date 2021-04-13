## Lab07

- Michael Muffoletto (q91w347)
- CSCI 476/594
- muffmike1@gmail.com
- 4/09/21

# Task 1.1
After generating the two output files out1.bin and out2.bin, I checked the diff between the two files which did not give me much information.   
<img width="983" alt="Screen Shot 2021-04-12 at 1 16 06 PM" src="https://user-images.githubusercontent.com/33213355/114449431-f2bd7d80-9b91-11eb-8690-d977e1ee98dd.png">   

After using the hex editor to look at each out file, I noticed that the files get padded with zeros.   
![Screen Shot 2021-04-12 at 1 20 31 PM](https://user-images.githubusercontent.com/33213355/114449458-fb15b880-9b91-11eb-8a9e-2dc059a91f50.png)   

# Task 1.2
The way that MD5 processing files is in blocks of size 64. Hence if a file is not 64 bits it will be padded in order to reach the desired size.   

# Task 1.3
Using the truncate command I was able to create a file that was exactly 64 bits, then I ran the md5collgen command on that txt file that created two new out3.bin and out4.bin files. After viewing the new files with a hex editor, I observed that no 00 padding is required.   
<img width="711" alt="Screen Shot 2021-04-12 at 1 28 53 PM" src="https://user-images.githubusercontent.com/33213355/114450552-61e7a180-9b93-11eb-9c68-59f66ecd058d.png">   
![Screen Shot 2021-04-12 at 1 31 16 PM](https://user-images.githubusercontent.com/33213355/114450578-6a3fdc80-9b93-11eb-9336-92217eb99bc6.png)   

# Task 1.4
After observing both out3.bin and out4.bin files, it appears that there is no difference between the two files. All the bits are the same, I predict that this might cause some sort of error in a future task.   
![Screen Shot 2021-04-12 at 1 31 16 PM](https://user-images.githubusercontent.com/33213355/114450578-6a3fdc80-9b93-11eb-9336-92217eb99bc6.png)

# Task 2
In this task I am asked to show that even if I create and hash files I can still change the contents of what is in the files while getting the same hashes for the two binary files. First I created two new fout1.bin and fout2.bin files. Then I ran the MD5sum command in order to make sure the files are equal to eachother which we find out they are.   
<img width="585" alt="Screen Shot 2021-04-12 at 1 49 45 PM" src="https://user-images.githubusercontent.com/33213355/114452668-f521d680-9b95-11eb-829c-dadc6919e003.png">   
Next I concatenated word "test" into each file to change them. This resulted in the file changing, but the hashes are still the same.   
<img width="528" alt="Screen Shot 2021-04-12 at 1 51 21 PM" src="https://user-images.githubusercontent.com/33213355/114453050-5e094e80-9b96-11eb-93cf-553530ba5736.png">   

# Task 3
In order start this task, first I compiled the code print_array.c that was given in the lab then I grabbed the head of the program. Next I took the head of the file and saved it as the prefix as well as the tail which was saved as the suffix and ran MD5collgen on the program in order to create some out files.   
<img width="515" alt="Screen Shot 2021-04-13 at 12 21 40 PM" src="https://user-images.githubusercontent.com/33213355/114601794-28766b00-9c53-11eb-9448-2b4ae3683964.png">   

After looking at the hash tables of these newly created programs, we note that the files are the same MD5 hash, but with different suffix's.   
![Screen Shot 2021-04-12 at 7 39 48 PM](https://user-images.githubusercontent.com/33213355/114484125-dee03e80-9bc6-11eb-8d1e-2ae58cb046a0.png)   
![Screen Shot 2021-04-12 at 7 39 52 PM](https://user-images.githubusercontent.com/33213355/114484152-e99ad380-9bc6-11eb-82b5-a3eebeb7ba68.png)   

Next I concatenated the prefix and suffix with these two files in order to create arr1.out and arr2.out   
<img width="451" alt="Screen Shot 2021-04-13 at 12 21 54 PM" src="https://user-images.githubusercontent.com/33213355/114602028-64113500-9c53-11eb-908c-91c9edab78a9.png">   

Finally, we run the two programs to verify that they are indeed different.   
<img width="1420" alt="Screen Shot 2021-04-13 at 12 08 03 PM" src="https://user-images.githubusercontent.com/33213355/114599961-07ad1600-9c51-11eb-8da9-d4048d5e266d.png">   

# Task 4
In order to successfully execute this task, first we compile the benign_evil.c file. Then we check the contents of the binary to see that the first array starts at 12,352. So we use similar commands in Task 3 for cutting the head and MD5 hash.  
<img width="528" alt="Screen Shot 2021-04-13 at 12 48 03 PM" src="https://user-images.githubusercontent.com/33213355/114604742-82c4fb00-9c56-11eb-899c-04b6cf970f5a.png">   

Next we want to create two new files that we can grad the middle section of. We use the head function again and do the same for the offset of the middle and the end. Then we concatenate them all together and check MD5sum to verify they are the same. After verifying that they are the same we chmod the programs to make them executable and run them to make sure we completed the task correctly.   
<img width="477" alt="Screen Shot 2021-04-13 at 12 55 55 PM" src="https://user-images.githubusercontent.com/33213355/114605736-a177c180-9c57-11eb-827b-6e70f138308c.png">   



