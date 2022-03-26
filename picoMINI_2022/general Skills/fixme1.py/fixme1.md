# fixme1.py
## Problem
Fix the syntax error in this Python script to print the flag:

https://artifacts.picoctf.net/c/42/fixme1.py
## Solution
After downloading, i try to run it on the terminal by 'python3 fixme1.py'. But it has error message: 

![fixme1](https://user-images.githubusercontent.com/84562630/160230593-b7da03b9-23af-4fbe-8925-28c01fb1836d.PNG)

Error is 'unexpected indent'. So i open it on the vim and fix it, you can see here that 'print' is abnormally indented. 

![fix2](https://user-images.githubusercontent.com/84562630/160230701-b6137613-3685-4d34-a8da-4f917a87b36c.PNG)

After fixing: 

![fix3](https://user-images.githubusercontent.com/84562630/160230740-21d956a2-50ae-4ed8-a3c7-16632c0cba21.PNG)

Then i save it and run: 

![fix4](https://user-images.githubusercontent.com/84562630/160230790-096ef9a4-bef6-400b-8398-fe64f34d1c3b.PNG)
## Flag
picoCTF{1nd3nt1ty_cr1515_e3881c95}
