## Objetivo 
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)
## Solución
```bash
luispuentes-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2024-02-27 18:22:41--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.16, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                        100%[======================================================================================================>]     270  --.-KB/s    in 0s      

2024-02-27 18:22:41 (7.79 MB/s) - 'runme.py' saved [270/270]

luispuentes-picoctf@webshell:~$ python3 runme.py 
picoCTF{run_s4n1ty_run}
luispuentes-picoctf@webshell:~$
```
## Notas
wget sirve para obtener los archivos desde un link

## Referencias
Manual de usuario del comando wget