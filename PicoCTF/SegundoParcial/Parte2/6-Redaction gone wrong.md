## Objetivo 
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/redactiongonewrong]
└─$ ls
Financial_Report_for_ABC_Labs.pdf
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/redactiongonewrong]
└─$ open Financial_Report_for_ABC_Labs.pdf    
```

picoCTF{C4n_Y0u_S33_m3_fully}
## Notas
La contraseña esta tapada por un recuadro en negro pero al seleccionar el texto en el pdf, se muestra la contraseña oculta por el recuadro.
