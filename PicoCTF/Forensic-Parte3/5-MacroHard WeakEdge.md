## Objetivo 
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/c00c449c3b08daaccacca6f9d5c55d49/Forensics%20is%20fun.pptm)

## Solución
```bash
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard$ ls
'Forensics is fun.pptm'  '[Content_Types].xml'   _rels   docProps   ppt
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard$ ls -la
total 112
drwxrwxrwx 1 luisillo luisillo   4096 Mar 22 11:38  .
drwxrwxrwx 1 luisillo luisillo   4096 Mar 22 11:35  ..
-rwxrwxrwx 1 luisillo luisillo 100093 Mar 23  2021 'Forensics is fun.pptm'
-rwxrwxrwx 1 luisillo luisillo  10660 Jan  1  1980 '[Content_Types].xml'
drwxrwxrwx 1 luisillo luisillo   4096 Mar 22 11:38  _rels
drwxrwxrwx 1 luisillo luisillo   4096 Mar 22 11:38  docProps
drwxrwxrwx 1 luisillo luisillo   4096 Mar 22 11:38  ppt
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard$ grep -r pico
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard$ cd ppt/
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard/ppt$ ls
_rels          presentation.xml  slideMasters  tableStyles.xml  vbaProject.bin
presProps.xml  slideLayouts      slides        theme            viewProps.xml
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard/ppt$ cd slideMasters/
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard/ppt/slideMasters$ ls
_rels  hidden  slideMaster1.xml
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard/ppt/slideMasters$ cat hidden
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Qluisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard/ppt/slideMasters$ cat hidden | tr -d ' ' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/macrohard/ppt/slideMasters$

```

picoCTF{D1d_u_kn0w_ppts_r_z1p5}
## Notas
Se estuvo explorando en las carpetas descomprimidas del archivo de power point hasya encontrar algo interesante, en este caso fue el archivo hidden, donde contenia una cadena que si se le eliminaban los espacios en blanco, y se le convertia de base 64, nos daba la bandera

## Referencias
https://www.reviversoft.com/es/file-extensions/pptm