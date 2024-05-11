## Objetivo 
I wonder what this really is... [enc](https://mercury.picoctf.net/static/1d8a5a2779c4dc24999f0358d7a1a786/enc) 
`''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/transformation]
└─$ ls
enc
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/transformation]
└─$ cat enc          
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥㜰㍢㐸㙽                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/transformation]
└─$ python3        
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> enc=open("enc").read()
>>> print(enc)
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥㜰㍢㐸㙽
>>> print(hex(ord(enc[0])))
0x7069
>>> for c in enc:
...     print(hex(ord(c)).lstrip("0x"),end='')
... 
7069636f4354467b31365f626974735f696e73743334645f6f665f385f65373033623438367d>>> 

```

picoCTF{16_bits_inst34d_of_8_e703b486}
## Notas
literalmente se va transformando la cadena dada, en un entero, despues a hexadecimal y finalmente a ascii

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=NzA2OTYzNmY0MzU0NDY3YjMxMzY1ZjYyNjk3NDczNWY2OTZlNzM3NDMzMzQ2NDVmNmY2NjVmMzg1ZjY1MzczMDMzNjIzNDM4MzY3ZA&oenc=65001