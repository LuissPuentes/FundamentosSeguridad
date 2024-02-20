## Objetivo 
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

## Datos de acceso
bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
## Solución
```
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
```

## Notas
esta tecnica se llama rot13, que rota las letras en una cadena 13 veces para codificar dicha cadena

## Referencias
[Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)
Manual de ayuda del comando tr 