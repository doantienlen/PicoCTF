# Glitch Cat 
## Problem 
Out flag printing service has started glitching! 

$ nc saturn.picoctf.net 65353
## Solution 
I run this service by terminal, it gives a flag, but the flag format si "chr(0xX)" ascii. 

![glitch1](https://user-images.githubusercontent.com/84562630/160231855-ef8a18a6-b05a-45dc-bccd-bc73c9cbdd0c.PNG)

Now i will write a python code to convert from chr to str and run this code.  

```python
x=['picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}']
flag = ""
for i in x: 
	if i == chr: 
  	  i = str(i)
	flag += i
print(flag)

```
![gith2](https://user-images.githubusercontent.com/84562630/160231945-de17e02c-0caf-4b92-9655-7d1c9c895754.PNG)

## Flag
picoCTF{gl17ch_m3_n07_9c42a45d}
