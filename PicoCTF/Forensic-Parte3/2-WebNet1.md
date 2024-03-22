## Objetivo 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Solución
```bash
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/webnet1$ ls -la
total 96
drwxrwxrwx 1 luisillo luisillo  4096 Mar 22 11:00 .
drwxrwxrwx 1 luisillo luisillo  4096 Mar 22 11:00 ..
-rwxrwxrwx 1 luisillo luisillo 92525 Oct 26  2020 capture.pcap
-rwxrwxrwx 1 luisillo luisillo  1704 Oct 26  2020 picopico.key
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/webnet1$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A3
    61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73    ag: picoCTF{this
    2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61    .is.not.your.fla
    67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74    g.anymore}..Cont
    65 6e 74 2d 4c 65 6e 67 74 68 3a 20 38 34 37 0d    ent-Length: 847.
--
    67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e    g: picoCTF{this.
    69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67    is.not.your.flag
    2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65    .anymore}..Conte
    6e 74 2d 4c 65 6e 67 74 68 3a 20 31 30 30 0d 0a    nt-Length: 100..
--
    Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
    Keep-Alive: timeout=5, max=99
    Connection: Keep-Alive
    Content-Type: image/jpeg
--
    00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b    ........picoCTF{
    68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65    honey.roasted.pe
    61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f    anuts}......ICC_
    50 52 4f 46 49 4c 45 00 01 01 00 00 02 0c 6c 63    PROFILE.......lc
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/webnet1$
```

picoCTF{honey.roasted.peanuts}
## Notas
Se utilizo el mismo comando que en el reto webnet0

## Referencias
Manual de usuario del comando ssldump