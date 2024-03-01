## Objetivo 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.
## Solución
```bash
luispuentes-picoctf@webshell:~$ nano level1.py
luispuentes-picoctf@webshell:~$ python3 level1.py 
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
luispuentes-picoctf@webshell:~$
```
## Notas
Con nano podemos ver el codigo y editarlo de un archivo

en el archivo especifica en un if, cual es la contraseña correcta

