# Serpentine 
## Problem 
Find the flag in the Python script! 
https://artifacts.picoctf.net/c/96/serpentine.py
## Solution 
After downloading, i run the code with terminal. i see that: 

![image](https://user-images.githubusercontent.com/84562630/160248719-53187bb5-0405-48cf-a349-cb988b7f19cf.png)

It's like a game. I try to choose "b" to get the flag, but it show a message:

![image](https://user-images.githubusercontent.com/84562630/160248862-ba4226db-0655-4e95-bce7-d6933c8ab670.png)

So i open this code by sumbtext: 
```python 

import random
import sys



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5c) + chr(0x01) + chr(0x57) + chr(0x2a) + chr(0x17) + chr(0x5e) + chr(0x5f) + chr(0x0d) + chr(0x3b) + chr(0x19) + chr(0x56) + chr(0x5b) + chr(0x5e) + chr(0x36) + chr(0x53) + chr(0x07) + chr(0x51) + chr(0x18) + chr(0x58) + chr(0x05) + chr(0x57) + chr(0x11) + chr(0x3a) + chr(0x0c) + chr(0x5d) + chr(0x5c) + chr(0x52) + chr(0x42) + chr(0x50) + chr(0x5a) + chr(0x5d) + chr(0x14)


def print_flag():
  flag = str_xor(flag_enc, 'enkidu')
  print(flag)


def print_encouragement():
  encouragements = ['You can do it!', 'Keep it up!', 
                    'Look how far you\'ve come!']
  choice = random.choice(range(0, len(encouragements)))
  print('\n-----------------------------------------------------')
  print(encouragements[choice])
  print('-----------------------------------------------------\n\n')



def main():

  print(
'''
    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \\
                   /   /               \  \\
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~
'''
  )
  print('Welcome to the serpentine encourager!\n\n')
  
  while True:
    print('a) Print encouragement')
    print('b) Print flag')
    print('c) Quit\n')
    choice = input('What would you like to do? (a/b/c) ')
    
    if choice == 'a':
      print_encouragement()
      
    elif choice == 'b':
      print('\nOops! I must have misplaced the print_flag function! Check my source code!\n\n')
      
    elif choice == 'c':
      sys.exit(0)
      
    else:
      print('\nI did not understand "' + choice + '", input only "a", "b" or "c"\n\n')



if __name__ == "__main__":
  main()

```
What i see is a flag with the form: 
```python 
flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5c) + chr(0x01) + chr(0x57) + chr(0x2a) + chr(0x17) + chr(0x5e) + chr(0x5f) + chr(0x0d) + chr(0x3b) + chr(0x19) + chr(0x56) + chr(0x5b) + chr(0x5e) + chr(0x36) + chr(0x53) + chr(0x07) + chr(0x51) + chr(0x18) + chr(0x58) + chr(0x05) + chr(0x57) + chr(0x11) + chr(0x3a) + chr(0x0c) + chr(0x5d) + chr(0x5c) + chr(0x52) + chr(0x42) + chr(0x50) + chr(0x5a) + chr(0x5d) + chr(0x14)
```
and a decode it funtion: 
```python 

def print_flag():
  flag = str_xor(flag_enc, 'enkidu')
  print(flag)
```

however this funtion has not been called in "b" funtion. Now, i will add it in 'b' funtion. 

![image](https://user-images.githubusercontent.com/84562630/160249183-ad4038c1-7762-45ba-aaf8-e99e0a8a4cf0.png)

And save and run it: 

![image](https://user-images.githubusercontent.com/84562630/160249230-df7bb92b-b012-44ee-86a1-fd4b46c84a09.png)

## Flag
picoCTF{7h3_r04d_l355_7r4v3l3d_b6567546}






