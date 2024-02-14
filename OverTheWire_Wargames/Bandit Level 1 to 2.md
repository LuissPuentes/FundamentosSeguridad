## Objetivo 
The password for the next level is stored in a file called **-** located in the home directory

## Datos de acceso
bandit1
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
## Solución
```
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```
## Notas
- al usar el comando cat en un documento cuyo nombre inicia con digito que no es una letra o un numero no funcionara, se requiere anteponer al nombre del archivo un punto y una diagonal ( ./ ) para que pueda ser abierto.

## Referencias
- [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
- [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)
