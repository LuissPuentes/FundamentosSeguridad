## Objetivo 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.

## Solución
```bash
luispuentes-picoctf@webshell:~$ ls
Parcial1  README.txt  level2.flag.txt.enc  level2.py
luispuentes-picoctf@webshell:~$ nano level2.py
luispuentes-picoctf@webshell:~$ python3 level2.py 
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}
luispuentes-picoctf@webshell:~$
```
## Notas
hay que convertir de charcode la contraseña que se muestra en el documento level2.py

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Charcode('Space',16)&input=MHgzMyAweDM5IDB4NjMgMHg2NSAK
