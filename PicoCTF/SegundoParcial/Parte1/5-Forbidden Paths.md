## Objetivo 
Can you get the flag?Here's the [website](http://saturn.picoctf.net:55793/).We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

## Solución
```bash
picoCTF{7h3_p47h_70_5ucc355_e5a6fcbc}
```
## Notas
en la pagina se solicita el archivo flag.txt pero nos dice que no esta autorizado, por lo que se ingresa al archivo mediante ../../../../flag.txt subiendo niveles de directorios para poder leer el archivo saltándose la barrera de privacidad.
