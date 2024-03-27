## Objetivo 
The developer of this website mistakenly left an important artifact in the website source, can you find it?The website is [here](http://saturn.picoctf.net:65086/)

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/searchSource]
└─$ ls
                                                                             
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/searchSource]
└─$ wget -r http://saturn.picoctf.net:65086/
...

┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/searchSource]
└─$ ls                                     
saturn.picoctf.net:65086
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/searchSource]
└─$ grep -R pico saturn.picoctf.net:65086
saturn.picoctf.net:65086/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/searchSource]
└─$ 

```

## Notas
 `wget -r` se utiliza para descargar de forma recursiva un sitio web completo, incluyendo todos los archivos y subdirectorios.

con grep -R permite buscar de manera recursiva en todos los archivos y subdirectorios dentro de un directorio dato.
## Referencias
Manual de usuario del comando grep.
Manual de usuario del comando wget.