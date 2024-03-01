## Objetivo 
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static)? This [BASH script](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh) might help!
## Solución
```bash
luispuentes-picoctf@webshell:~$ ls -la 
total 56
drwxr-xr-x 2 luispuentes-picoctf luispuentes-picoctf   147 Feb 26 18:49 .
drwxr-xr-x 3 root                root                   33 Feb 26 18:18 ..
-rw-r--r-- 1 luispuentes-picoctf luispuentes-picoctf   220 Feb 26 18:18 .bash_logout
-rw-r--r-- 1 luispuentes-picoctf luispuentes-picoctf  3771 Feb 26 18:18 .bashrc
-rw-r--r-- 1 luispuentes-picoctf luispuentes-picoctf   807 Feb 26 18:18 .profile
-rw-rw-r-- 1 luispuentes-picoctf luispuentes-picoctf   167 Feb 26 18:20 .wget-hsts
-rw-r--r-- 1 root                root                 4443 Feb 26 18:34 README.txt
-rw-rw-r-- 1 luispuentes-picoctf luispuentes-picoctf    34 Mar 16  2021 flag
-rw-rw-r-- 1 luispuentes-picoctf luispuentes-picoctf   785 Mar 16  2021 ltdis.sh
-rw-rw-r-- 1 luispuentes-picoctf luispuentes-picoctf  8376 Mar 16  2021 static
-rwxrwxr-x 1 luispuentes-picoctf luispuentes-picoctf 10936 Mar 16  2021 warm
luispuentes-picoctf@webshell:~$ cat^C
luispuentes-picoctf@webshell:~$ cat ltdis.sh
#!/bin/bash



echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by 
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
        echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

        echo "Ripping strings from binary with file offsets..."
        strings -a -t x $1 > $1.ltdis.strings.txt
        echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"



else
        echo "Disassembly failed!"
        echo "Usage: ltdis.sh <program-file>"
        echo "Bye!"
fi
luispuentes-picoctf@webshell:~$ ./ltdis.sh
-bash: ./ltdis.sh: Permission denied
luispuentes-picoctf@webshell:~$ cat static | strings | grep pico
picoCTF{d15a5m_t34s3r_ae0b3ef2}
luispuentes-picoctf@webshell:~$
```
## Notas
strings extrae las cadenas de un archivo binario

## Referencias
https://www.howtogeek.com/427805/how-to-use-the-strings-command-on-linux/