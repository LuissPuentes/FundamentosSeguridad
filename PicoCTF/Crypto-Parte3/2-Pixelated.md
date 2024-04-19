## Objetivo 
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png)

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/pixelated]
└─$ ls
scrambled1.png  scrambled2.png
                                                                                                                                                                      
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/pixelated]
└─$ java -jar /opt/stegsolve.jar 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

```

picoCTF{d562333d}
## Notas
- stegsolve es una herramienta que nos ayuda a combinar imagenes.

## Referencias
https://en.wikipedia.org/wiki/Visual_cryptography

https://github.com/zardus/ctf-tools/blob/master/stegsolve/install