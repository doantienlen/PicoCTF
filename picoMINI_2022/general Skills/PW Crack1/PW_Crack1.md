# PW Crack 1
## Problem 
Can you crack the password to get the flag?
Download the password checker https://artifacts.picoctf.net/c/53/level1.py and you'll need the encrypted https://artifacts.picoctf.net/c/53/level1.flag.txt.enc in the same directory too. 
## Solution 
After downloading, i run this code by the terminal, but it asks for password. 

Then i open it by the Vim.

```python 
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "8713"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()

```
After i read this code, i found that if i enter the password as "8713", 

![image](https://user-images.githubusercontent.com/84562630/160232882-89d7f578-e18e-47e1-bccf-ce11dab74bd5.png)

the flag appears: 

![image](https://user-images.githubusercontent.com/84562630/160232904-e030f4d9-fa58-4803-981b-2ba790be1254.png)
## Flag
picoCTF{545h_r1ng1ng_1b2fd683}

