## Objetivo 
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.

## Solución
```bash
luispuentes-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 4427 | grep pico
picoCTF{digital_plumb3r_5ea1fbd7}
^C
luispuentes-picoctf@webshell:~$
```
## Notas
nc - es un comando que permite acceder a puertos TCP o UDP de la propia máquina o de otras máquinas remotas.

## Referencias
https://www.ochobitshacenunbyte.com/2021/11/04/uso-del-comando-ncat-nc-en-linux-con-ejemplos/
