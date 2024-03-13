## Objetivo 
This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.

## Solución
```bash
┌──(luispuentes㉿kali)-[~/Downloads]
└─$ ls
Compact-Wireless-Kali-Linux-App  cacert.der  garden.jpg

┌──(luispuentes㉿kali)-[~/Downloads]
└─$ hexeditor garden.jpg 

┌──(luispuentes㉿kali)-[~/Downloads]
└─$ sudo apt install gimp
[sudo] password for luispuentes: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package gimp

┌──(luispuentes㉿kali)-[~/Downloads]
└─$ strings -n 10 garden.jpg | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y33dd2eEF5}"

```


## Notas
se obtienen las cadenas en el archivo png que tiene ocultas filtrando la palabra pico

## Referencias
https://linux.ciberaula.com/articulo/gimp/