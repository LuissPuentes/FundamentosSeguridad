## Objetivo 
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Datos de acceso
bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
## Solución
```
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ cat data.txt | base64
VkdobElIQmhjM04zYjNKa0lHbHpJRFo2VUdWNmFVeGtVakpTUzA1a1RsbEdUbUkyYmxaRFMzcHdh
R3hZU0VKTkNnPT0K
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$
```

## Notas
base64 es un comando para codificar o decodificar archivos, salidas o entradas
con -d se especifica que decodifique 

## Referencias
[Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64) 