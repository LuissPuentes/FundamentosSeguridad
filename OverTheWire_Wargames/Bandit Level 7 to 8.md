## Objetivo 
The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Datos de acceso
bandit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
## Solución
``` bash 
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$
```

## Notas
- wc -l cuenta las lineas de un archivo de texto
- head muestra las primeras 10 lineas
- tail muestra las ultimas 10 lineas
- grep filtra las lineas en base a un patron
- 
## Referencias
https://www.freecodecamp.org/espanol/news/grep-command-tutorial-how-to-search-for-a-file-in-linux-and-unix-with-recursive-find/

Manual de ayuda del comando grep