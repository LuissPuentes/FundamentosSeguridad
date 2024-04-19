## Objetivo 
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/basic-mod1]
└─$ cat message.txt 
350 63 353 198 114 369 346 184 202 322 94 235 114 110 185 188 225 212 366 374 261 213                                                                                                                                                                        
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/basic-mod1]
└─$ python3 exp.py 
['350', '63', '353', '198', '114', '369', '346', '184', '202', '322', '94', '235', '114', '110', '185', '188', '225', '212', '366', '374', '261', '213']


┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/basic-mod1]
└─$ python3 exp.py
['350', '63', '353', '198', '114', '369', '346', '184', '202', '322', '94', '235', '114', '110', '185', '188', '225', '212', '366', '374', '261', '213']
17
26
20
13
3
36
13
36
17
26
20
13
3
36
0
3
3
27
33
4
2
28


┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/basic-mod1]
└─$ python3 -c 'print(ord("A"))'
65
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/basic-mod1]
└─$ python3 exp.py                
['350', '63', '353', '198', '114', '369', '346', '184', '202', '322', '94', '235', '114', '110', '185', '188', '225', '212', '366', '374', '261', '213']
RRUNDDNNRRUNDDADDDDECC


┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/basic-mod1]
└─$ python3 -c 'print(ord("0"))'
48
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/basic-mod1]
└─$ python3 -c 'print(48-26)'   
22
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/basic-mod1]
└─$ python3 exp.py              
['350', '63', '353', '198', '114', '369', '346', '184', '202', '322', '94', '235', '114', '110', '185', '188', '225', '212', '366', '374', '261', '213']
R0UND_N_R0UND_ADD17EC2
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/crypto/basic-mod1]
└─$ python3 exp.py
['350', '63', '353', '198', '114', '369', '346', '184', '202', '322', '94', '235', '114', '110', '185', '188', '225', '212', '366', '374', '261', '213']
picoCTF{R0UND_N_R0UND_ADD17EC2}

```

exp.py
```
datos = open('message.txt').read().split()

flag = ''

print (datos)

for n in datos:
        c = int(n) % 37
        if c >= 0 and c <= 25:
                s = chr(c+65)
        elif c >= 26 and c <= 35:
                s = chr(c+22)
        elif c == 36:
                s = '_'
        flag += s
print(f"picoCTF{{{flag}}}")
```
## Notas
- mod 37 significa módulo 37. Da el resto de un número después de dividirlo por 37.
