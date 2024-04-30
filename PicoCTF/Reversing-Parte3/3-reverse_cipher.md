## Objetivo 
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). Can you reverse the flag.

## Solución
```bash
──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ ls
rev  rev_this
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ chmod +x rev  
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ ./rev  
No flag found, please make sure this is run on the server
zsh: segmentation fault  ./rev
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ cat rev_this         
picoCTF{w1{1wq8/7376j.:}                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ touch flag.txt
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ ./rev         
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ ls
flag.txt  rev  rev_this

┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ cat rev_this
picoCTF{w1{1wq8/7376j.:}                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ python3                      
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 10 & 1
0
>>> 11 & 1
1
>>> 12 & 1
0
>>> 
KeyboardInterrupt
>>> 
zsh: suspended  python3

┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ nano exp.py   
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ python3 exp.py
picoCTF{r3v3rs312528e05}

┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/reversecipher]
└─$ cat exp.py       

d = open("rev_this").read()
flag = "picoCTF{"

for j in range (8,23):
        if j & 1 == 0:
                flag+=chr( ord( d[j] ) - 5) 

        else:
                flag+=chr( ord( d[j] ) + 2)
flag+="}"
print(flag)

```


## Notas
sudo apt install ghidra


## Referencias
https://hex-rays.com/ida-pro/