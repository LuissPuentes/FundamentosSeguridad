## Objetivo 
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

## Datos de acceso
bandit5
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
## Solución
```
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere02  maybehere04  maybehere06  maybehere08  maybehere10  maybehere12  maybehere14  maybehere16  maybehere18
maybehere01  maybehere03  maybehere05  maybehere07  maybehere09  maybehere11  maybehere13  maybehere15  maybehere17  maybehere19
bandit5@bandit:~/inhere$ find -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ find . -readable size 1033c -type f
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        bandit5@bandit:~/inhere$
```

## Notas
- si al usar el comando find, le agregamos -size y se le especifica el peso que estamos buscando, nos mostrara los documentos que tengan ese peso en especifico.
- ls -R lista archivos de manera recursiva
- find permite buscar archivos
- -readable nos da los archivos legibles (ASCII)
- el . permite que la busqueda sea hacia abajo
## Referencias

https://man7.org/linux/man-pages/man1/find.1.html

