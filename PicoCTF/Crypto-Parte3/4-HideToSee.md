## Objetivo 
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/238/atbash.jpg).

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/hidetosee]
└─$ ls
atbash.jpg
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/hidetosee]
└─$ open atbash.jpg  


┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/hidetosee]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/hidetosee]
└─$ ls   
atbash.jpg  encrypted.txt
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/hidetosee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_8z0uvwwx}
```

picoCTF{atbash_crack_8a0feddc}
## Notas
- Steghide es un programa de esteganografía que oculta bits de un archivo de datos en algunos de los bits menos significativos de otro archivo de tal manera que la existencia del archivo de datos no es visible y no se puede probar.

## Referencias
https://es.wikipedia.org/wiki/Atbash

https://www.kali.org/tools/steghide/

https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfOHowdXZ3d3h9DQo&ieol=CRLF&oeol=CRLF