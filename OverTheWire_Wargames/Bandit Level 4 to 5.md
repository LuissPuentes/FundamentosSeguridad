## Objetivo 
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Datos de acceso
bandit4
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
## Solución
```

bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere

bandit4@bandit:~/inhere$ cat ./*
QRrtZi      H|ȧ^7L3Yͯ   ŴEYܚ   V&hFO̫`\-⃐Hx2Kix#e>VOp{   MUb4gQeE}:gj8<.e��Se 0]7b<~G=1��B׃"W9ؽ5lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
K~+9"T*Z$"r
Z\жq7��/nbandit4@bandit:~/inhere$

bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ cat ./-file09
Z\жq7��/nbandit4@bandit:~/inhere$ cat ./-file08
K~+9"T*Z$"r
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$

```
## Notas
- Hay archivos que pueden contener datos que no son legibles para nosotros pero tal vez si para una computadora.
- con cat ./* lee todos los archivos
- file me dice de que tipo de archivo es su contenido
## Referencias
https://man7.org/linux/man-pages/man1/cat.1.html

