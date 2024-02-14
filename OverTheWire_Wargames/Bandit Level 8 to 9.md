## Objetivo 
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Datos de acceso
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
## Solución
```
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:
```

## Notas
- sort ordena lineas en un archivo de texto
- uniq -u filtra lineas que no se repiten
- uniq -c cuenta las ocurrencias de una linea
- uniq -d muestra solo las lineas repetidas
## Referencias
[Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)
https://francisconi.org/linux/comandos/sort

Manual de ayuda del comando Sort
Manual de ayuda del comando uniq