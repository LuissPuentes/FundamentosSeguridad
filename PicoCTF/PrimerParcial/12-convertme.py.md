## Objetivo 
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/22/convertme.py)
## Solución
```bash
luispuentes-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/22/convertme.py
--2024-02-26 22:29:57--  https://artifacts.picoctf.net/c/22/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                    100%[======================================================================================================>]   1.16K  --.-KB/s    in 0s      

2024-02-26 22:29:58 (504 MB/s) - 'convertme.py' saved [1189/1189]

luispuentes-picoctf@webshell:~$ python3 convertme.py 
If 98 is in decimal base, what is it in binary base?
Answer: 1100010
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
luispuentes-picoctf@webshell:~$
```


## Referencias
https://gchq.github.io/CyberChef/#recipe=To_Base(2)&input=OTg