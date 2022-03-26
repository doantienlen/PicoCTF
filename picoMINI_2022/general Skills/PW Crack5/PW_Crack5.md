# PW Crack 5
## Problem
Can you crack the password to get the flag? 
Download the password checker https://artifacts.picoctf.net/c/81/level5.py and you'll need to the encrypted https://artifacts.picoctf.net/c/81/level5.flag.txt.enc
and the https://artifacts.picoctf.net/c/81/level5.hash.bin in the same directory too. Here's a https://artifacts.picoctf.net/c/81/dictionary.txt with all possible 
passwords based on the password conventions we'se seen so far. 
## Solution 
After downloading the files. I try to run the level5 python code on the terminal. But it askes for password, so i open it by Vim. 

According to the title, there is a dictionary.txt file that can contain passwords. I open the dictionary.txt file, but it has a lot of possible password cases. 

After analzing the code, i try to add the following lines of code: 
```python 
def level_5_pw_check():
    # user_pw = input("Please enter correct password for flag: ")
    file = open('dictionary.txt','r')
    lst_pass = []
    for i in file: 
        data = i.strip()
        lst_pass.append(data)
    
    for i in lst_pass: 
        user_pw = i 
        user_pw_hash = hash_pw(user_pw)
        
        if( user_pw_hash == correct_pw_hash ):
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
        print("That password is incorrect")


```
And i run the program: 

![image](https://user-images.githubusercontent.com/84562630/160248507-88087295-5ac6-428f-8c81-d4a611137135.png)

## Flag
picoCTF{h45h_sl1ng1ng_fffcda23}





