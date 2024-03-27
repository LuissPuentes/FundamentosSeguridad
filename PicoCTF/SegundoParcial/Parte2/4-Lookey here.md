## Objetivo 
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/125/anthem.flag.txt).

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2]
└─$ mkdir lookeyhere
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2]
└─$ cd lookeyhere 
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/lookeyhere]
└─$ wget https://artifacts.picoctf.net/c/125/anthem.flag.txt 
--2024-03-27 16:54:31--  https://artifacts.picoctf.net/c/125/anthem.flag.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.85, 13.249.21.32, 13.249.21.66, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108668 (106K) [application/octet-stream]
Saving to: ‘anthem.flag.txt’

anthem.flag.txt                100%[====================================================>] 106.12K   172KB/s    in 0.6s    

2024-03-27 16:54:33 (172 KB/s) - ‘anthem.flag.txt’ saved [108668/108668]

                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/lookeyhere]
└─$ ls
anthem.flag.txt
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/lookeyhere]
└─$ cat anthem.flag.txt | grep pico     
      we think that the men of picoCTF{gr3p_15_@w3s0m3_58f5c024}
           
```


## Notas
se lee el archivo con un grep usando la palabra pico

## Referencias
Manual de usuario del comando grep