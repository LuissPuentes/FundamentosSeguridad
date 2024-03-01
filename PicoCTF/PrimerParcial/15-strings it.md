## Objetivo 
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

## Solución
```bash
luispuentes-picoctf@webshell:~$ cat strings | strings | grep pico
picoCTF{5tRIng5_1T_7f766a23}
luispuentes-picoctf@webshell:~$
```
## Notas
strings extrae las cadenas de un archivo binario
con el grep buscamos pico para buscar la cadena que contenga parte de la llave

## Referencias
manual de usuario del comando strings
https://linux.die.net/man/1/strings 