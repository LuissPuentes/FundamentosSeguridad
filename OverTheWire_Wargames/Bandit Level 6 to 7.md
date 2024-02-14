## Objetivo 
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
## Datos de acceso
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
## Solución
```bash
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c -type f 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$
```

## Notas
- en linux los archivos de errores les asigna el valor de 2, por lo que se especifica que si la busqueda encuentra ese tipo de archivos los reenvie a una carpeta llamada null  ( 2>/dev/null)(no apareceran en pantalla).
- al usar el comando find, e iniciar con una diagonal ( / ) permite que la busqueda se realize desde la raiz
- ls -la permite ver mas detalles de los archivos en un directorio
-  -user permite especificar usuario y -group permite especificar el grupo

## Referencias
https://man7.org/linux/man-pages/man1/find.1.html
https://askubuntu.com/questions/350208/what-does-2-dev-null-mean
