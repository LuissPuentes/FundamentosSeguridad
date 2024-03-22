## Objetivo 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Solución
```bash

luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/webnet0$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A3

    61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67    ag: picoCTF{nong
    73 68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63    shim.shrimp.crac
    6b 65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c    kers}..Content-L
    65 6e 67 74 68 3a 20 38 32 31 0d 0a 4b 65 65 70    ength: 821..Keep
--
    67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73    g: picoCTF{nongs
    68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63 6b    him.shrimp.crack
    65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c 65    ers}..Content-Le
    6e 67 74 68 3a 20 31 30 30 0d 0a 4b 65 65 70 2d    ngth: 100..Keep-
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/webnet0$

```
## Notas
En wireshark se abre la captura de paquetes y se van filtrando los paquetes, buscando strings y como clave picoCTF.

y tambien en consola con el comando ssldump podemos ubicar la solucion 
## Referencias
manual de usuario del comando ssldump