# PW Crack 2
## Problem
Can you crack the password to get the flag? 

Download the password checker https://artifacts.picoctf.net/c/16/level2.py and you'll need the encrypted https://artifacts.picoctf.net/c/16/level2.flag.txt.enc in the same directory too. 
## Solution
After downloading, i run it on the terminal, but it ask the password. 

I opend it by Vim and fixed it like this: 
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

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
#    user_pw = input("Please enter correct password for flag: ")
    pass_of_flag = [ chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ]
    user_pw  = ""
    for i in pass_of_flag: 
        i = str(i) 
        user_pw += i 
    print("pass is " + user_pw) 
    if( user_pw  == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ): 
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()

```
The part of the code i fixed. 

![leve3](https://user-images.githubusercontent.com/84562630/160234094-462f0c69-8df9-4fa5-82fc-fbee2eaa6a54.PNG)

then i run it. 

![leve2](https://user-images.githubusercontent.com/84562630/160234028-eab61d85-88e1-403c-875c-73410c12ba4d.PNG)
## Flag
picoCTF{tr45h_51ng1ng_489dea9a}
