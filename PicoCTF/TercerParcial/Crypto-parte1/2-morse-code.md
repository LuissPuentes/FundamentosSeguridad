## Objetivo 
Morse code is well known. Can you decrypt this?Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav).Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/morse-code]
└─$ ls
morse_chal.wav
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/morse-code]
└─$ python3
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> "WH47 H47H 90D W20U9H7".lower()
'wh47 h47h 90d w20u9h7'
>>> "WH47 H47H 90D W20U9H7".lower().replace(' ', '_')
'wh47_h47h_90d_w20u9h7'
>>> "picoCTF{WH47 H47H 90D W20U9H7}".lower().replace(' ', '_')
'picoctf{wh47_h47h_90d_w20u9h7}'
>>> 

```


## Notas
Se utilizo una pagina para decifrar el morse en el audio y ya despues solo se adecuo al formato de la bandera el resultado.

## Referencias
https://morsecode.world/international/decoder/audio-decoder-adaptive.html