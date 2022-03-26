# PW Crack 4
## Problem 
Can you crack the password to get the flag?
Download the password checker here and you'll need the encrypted https://artifacts.picoctf.net/c/61/level4.flag.txt.enc and the https://artifacts.picoctf.net/c/61/level4.hash.bin in the same directory too. 
There are 100 potential passwords with only 1 being correct. You can find these by examining the password checker script.
## Solution 
After downloading, i open it and try to run on the terminal, but is asks for password. 

I finded this code : 

![image](https://user-images.githubusercontent.com/84562630/160235278-74d718ec-c4c2-4b5f-ace6-4ff57879a50e.png)

The password can do one of these things, then i fixed the level3.py code as like this: 
```python 
def level_4_pw_check():
    pos_pw_list = ["fb81", "195e", "3c10", "a768", "ad1b", "fe1e", "33e3", "6a42", "aea5", "4ef0", "fb62", "4571", "5d9f", "d821", "5371", "19f3", "f276", "588d", "b5af", "e00f", "eb55", "324f", "3d25", "e4a9", "e2ac", "aef6", "fc3e", "2317", "38d3", "57a7", "1321", "9b89", "5b9d", "39b6", "bcc1", "5972", "683e", "5ba1", "ee01", "3198", "3946", "a73e", "c439", "4836", "b563", "bfb9", "bb28", "aee3", "bd58", "8d6c", "c3d3", "f973", "936e", "2186", "7ec0", "f9a3", "afff", "f832", "d7d4", "2017", "9887", "9d44", "6974", "eede", "a061", "22a7", "4524", "3079", "a85a", "7973", "4560", "5580", "929d", "386f", "8a9b", "9e9b", "41be", "9dc1", "c58e", "442c", "2b1a", "e864", "1239", "9c5a", "5333", "3d85", "4e25", "2624", "4c2f", "6cc8", "5e30", "f538", "963f", "e970", "3285", "b7d7", "7429", "4193", "659b", "3986"]    
    for i in pos_pw_list: 
        user_pw = i 
        user_pw_hash = hash_pw(user_pw)
        
        if( user_pw_hash == correct_pw_hash ):
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
        print("That password is incorrect")
```
and i run it: 

![image](https://user-images.githubusercontent.com/84562630/160235439-5d3f100a-7574-46cd-a09d-c855cbaa8441.png)
## Flag
picoCTF{fl45h_5pr1ng1ng_c8005223}


