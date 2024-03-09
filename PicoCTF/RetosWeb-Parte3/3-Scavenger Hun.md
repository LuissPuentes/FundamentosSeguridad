## Objetivo 
There is some interesting information hidden around this site [http://mercury.picoctf.net:55079/](http://mercury.picoctf.net:55079/). Can you find it?

## Solución
```bash
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}
```
La contraseña estaba oculta en el sitio web dividida en partes:
- En el codigo fuente estaba la primera parte **picoCTF{t**
- El el archivo myss.css estaba la segunda parte **h4ts_4_l0**
- En el robots ( http://mercury.picoctf.net:55079/robots.txt ) esta la tercera parte **t_0f_pl4c**
- En http://mercury.picoctf.net:55079/.htaccess esta la 4ta parte **3s_2_lO0k** 
- En http://mercury.picoctf.net:55079/.DS_Store esta la 5ta parte y final **_74cceb07}**

## Notas
- .htaccess es un archivo ubicado en un directorio donde se establecen configuraciones de seguridad para un directorio en particular.
- El estandar de exclusion de robots se encarga indicarle a los bots como el de google que no indexe parte de mi sitio.
- Existe un archivo llamado .DS_Store el cual almacena informacion de la configuracion de la carpeta donde este el archivo.
## Referencias
https://httpd.apache.org/docs/2.4/en/howto/htaccess.html
https://en.wikipedia.org/wiki/.DS_Store