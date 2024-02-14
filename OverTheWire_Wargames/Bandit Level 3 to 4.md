## Objetivo 
The password for the next level is stored in a hidden file in the **inhere** directory.
## Datos de acceso
bandit3
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Solución
```
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat ./.hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~/inhere$
```

## Notas
- con -a, el comando ls muestra todo lo que hay dentro de un directorio

## Referencias
https://man7.org/linux/man-pages/man1/cat.1.html
