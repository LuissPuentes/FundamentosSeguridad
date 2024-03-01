## Objetivo 
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/4/fixme2.py) 

## Solución
```bash
luispuentes-picoctf@webshell:~$ ls
Parcial1  README.txt  fixme2.py
luispuentes-picoctf@webshell:~$ cat fixme2.py 

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + chr(0x09) + chr(0x5f) + chr(0x1f) + chr(0x10) + chr(0x3b) + chr(0x1b) + chr(0x55) + chr(0x1a) + chr(0x34) + chr(0x5d) + chr(0x51) + chr(0x40) + chr(0x54) + chr(0x09) + chr(0x05) + chr(0x04) + chr(0x57) + chr(0x1b) + chr(0x11) + chr(0x31) + chr(0x0e) + chr(0x51) + chr(0x5c) + chr(0x44) + chr(0x51) + chr(0x0a) + chr(0x5b) + chr(0x5a) + chr(0x19)

  
flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag = "":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)


luispuentes-picoctf@webshell:~$ ./fixme2.py
-bash: ./fixme2.py: Permission denied
luispuentes-picoctf@webshell:~$ python3 fixme2.py 
  File "/home/luispuentes-picoctf/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
luispuentes-picoctf@webshell:~$ ^C
luispuentes-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
>>> import random
>>> 
>>> 
>>> 
>>> def str_xor(secret, key):
...     #extend key to secret length
...     new_key = key
...     i = 0
...     while len(new_key) < len(secret):
...         new_key = new_key + key[i]
...         i = (i + 1) % len(key)        
...     return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
... 
>>> 
>>> flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + chr(0x09) + chr(0x5f) + chr(0x1f) + chr(0x10) + chr(0x3b) + chr(0x1b) + chr(0x55) + chr(0x1a) + chr(0x34) + chr(0x5d) + chr(0x51) + chr(0x40) + chr(0x54) + chr(0x09) + chr(0x05) + chr(0x04) + chr(0x57) + chr(0x1b) + chr(0x11) + chr(0x31) + chr(0x0e) + chr(0x51) + chr(0x5c) + chr(0x44) + chr(0x51) + chr(0x0a) + chr(0x5b) + chr(0x5a) + chr(0x19)
>>> 
>>>   
>>> flag = str_xor(flag_enc, 'enkidu')
>>> 
>>> # Check that flag is not empty
>>> if flag == "":
...   print('String XOR encountered a problem, quitting.')
... else:
...   print('That is correct! Here\'s your flag: ' + flag)
... 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
```
## Notas
el error estaba en la comparacion del if   `if flag == "":` ya que le faltaba el doble ==