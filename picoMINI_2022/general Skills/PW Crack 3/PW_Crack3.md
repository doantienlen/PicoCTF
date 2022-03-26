# PW Crack 3
## Problem
Can you crack the password to get the flag? 
Download the password checker https://artifacts.picoctf.net/c/27/level3.py  and you'll need the encrypted https://artifacts.picoctf.net/c/27/level3.flag.txt.enc  and the https://artifacts.picoctf.net/c/27/level3.hash.bin in the same directory too.

There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Solution 
After downloading, i run it by the terminal, but it ask password. 

I open it with sublime text. i see this list

![image](https://user-images.githubusercontent.com/84562630/160234682-6cbd6e42-816d-4cc7-8df0-57ebcfd311bb.png)

as suggested by the beginning of the post, the password is one of these seven codes. And i fixed as like this: 

![image](https://user-images.githubusercontent.com/84562630/160234754-3619dba2-57a6-4e06-8350-a4c66f81495f.png)

and i saved and runed it: 

![image](https://user-images.githubusercontent.com/84562630/160234773-1edc929a-540f-4075-987f-11a216f2ba56.png)
## Flag
picoCTF{m45h_fl1ng1ng_5a6e8955}
