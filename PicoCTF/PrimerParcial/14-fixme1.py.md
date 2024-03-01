## Objetivo 
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py) 

## Solución
```bash
luispuentes-picoctf@webshell:~$ python3 fixme1.py
  File "/home/luispuentes-picoctf/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
luispuentes-picoctf@webshell:~$ 
luispuentes-picoctf@webshell:~$ 
luispuentes-picoctf@webshell:~$ cat fixme1.py

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06) + chr(0x1c) + chr(0x5a) + chr(0x5c) + chr(0x55) + chr(0x40) + chr(0x3a) + chr(0x5f) + chr(0x53) + chr(0x5b) + chr(0x57) + chr(0x41) + chr(0x57) + chr(0x08) + chr(0x5c) + chr(0x14)

  
flag = str_xor(flag_enc, 'enkidu')
  print('That is correct! Here\'s your flag: ' + flag)

luispuentes-picoctf@webshell:~$ ^C
luispuentes-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import random
>>> 
>>> def str_xor(secret, key):
...     # Extend key to secret length
...     new_key = key
...     i = 0
...     while len(new_key) < len(secret):
...         new_key = new_key + key[i]
...         i = (i + 1) % len(key)        
...     return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c, new_key_c) in zip(secret, new_key)])
... 
>>> flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06) + chr(0x1c) + chr(0x5a) + chr(0x5c) + chr(0x55) + chr(0x40) + chr(0x3a) + chr(0x5f) + chr(0x53) + chr(0x5b) + chr(0x57) + chr(0x41) + chr(0x57) + chr(0x08) + chr(0x5c) + chr(0x14)
>>> 
>>> flag = str_xor(flag_enc, 'enkidu')
>>> print('That is correct! Here\'s your flag: ' + flag)
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
```


## Notas
El error estaba en la indentación de la última línea que contenía la función `print`.
La línea `print` estaba indentada un nivel más allá de lo que debería haber estado, lo cual es un error de sintaxis en Python.
