## Objetivo 
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag).

## Solución
```bash
luispuentes-picoctf@webshell:~$ ls
README.txt
luispuentes-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag
--2024-02-26 18:20:17--  https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                                            100%[======================================================================================================>]      34  --.-KB/s    in 0s      

2024-02-26 18:20:17 (18.2 MB/s) - 'flag' saved [34/34]

luispuentes-picoctf@webshell:~$ ls
README.txt  flag
luispuentes-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_4a2b35fd}
luispuentes-picoctf@webshell:~$
```

## Notas
wget me permite descargar un archivo directamente en la consola
## Referencias
Manual de usuario del comando wget.