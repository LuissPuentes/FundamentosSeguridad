## Objetivo 
Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/159/cipher.txt) using this key "CYLAB".

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/vigenere]
└─$ ls
cipher.txt
                                                                                                                                                                      
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/vigenere]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_f85729e7}
```

picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_d85729g7}
## Notas
en cyberchef se le pasa el texto cifrado y la llave y nos da el texto decifrado.

## Referencias
https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher

https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfZjg1NzI5ZTd9