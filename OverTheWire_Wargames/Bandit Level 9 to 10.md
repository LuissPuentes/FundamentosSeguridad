## Objetivo 
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos de acceso
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solución

```
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ cat data.txt | strings | grep ==
x]T========== theG)"
========== passwordk^
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
```
## Notas
strings extrae las cadenas de un archivo binario

## Referencias
https://www.howtogeek.com/427805/how-to-use-the-strings-command-on-linux/