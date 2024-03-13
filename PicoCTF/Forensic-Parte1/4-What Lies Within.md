## Objetivo 
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

## Solución
```bash
┌──(luispuentes㉿kali)-[~/picoctf/forensic/WhatLiesWithin]
┌──(luispuentes㉿kali)-[~/picoctf/forensic/WhatLiesWithin]
└─$ ls
buildings.png

┌──(luispuentes㉿kali)-[~/picoctf/forensic/WhatLiesWithin]
└─$ open buildings.png 

┌──(luispuentes㉿kali)-[~/picoctf/forensic/WhatLiesWithin]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"


```


## Notas
zsteg  es una herramienta que nos permite detectar algun tipo de steganografia que se este usando en el archivo
Tambien hay paginas en linea qu enos permiten hacer lo mismo


## Referencias
https://latam.kaspersky.com/resource-center/definitions/what-is-steganography
https://stylesuxx.github.io/steganography/