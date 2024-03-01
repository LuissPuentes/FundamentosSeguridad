## Objetivo 
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip) 

## Solución
```bash
luispuentes-picoctf@webshell:~$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
luispuentes-picoctf@webshell:~$ ls -la
total 68
drwxr-xr-x 3 luispuentes-picoctf luispuentes-picoctf  4096 Feb 26 19:00 .
drwxr-xr-x 3 root                root                   33 Feb 26 18:18 ..
-rw-r--r-- 1 luispuentes-picoctf luispuentes-picoctf   220 Feb 26 18:18 .bash_logout
-rw-r--r-- 1 luispuentes-picoctf luispuentes-picoctf  3771 Feb 26 18:18 .bashrc
-rw-r--r-- 1 luispuentes-picoctf luispuentes-picoctf   807 Feb 26 18:18 .profile
-rw-rw-r-- 1 luispuentes-picoctf luispuentes-picoctf   167 Feb 26 18:20 .wget-hsts
drwxr-xr-x 3 luispuentes-picoctf luispuentes-picoctf    28 Mar 16  2021 Addadshashanammu
-rw-rw-r-- 1 luispuentes-picoctf luispuentes-picoctf  4521 Mar 16  2021 Addadshashanammu.zip
-rw-r--r-- 1 root                root                 4443 Feb 26 18:34 README.txt
-rw-rw-r-- 1 luispuentes-picoctf luispuentes-picoctf    34 Mar 16  2021 flag
-rw-rw-r-- 1 luispuentes-picoctf luispuentes-picoctf   785 Mar 16  2021 ltdis.sh
-rw-rw-r-- 1 luispuentes-picoctf luispuentes-picoctf  8376 Mar 16  2021 static
-rwxrwxr-x 1 luispuentes-picoctf luispuentes-picoctf 10936 Mar 16  2021 warm
luispuentes-picoctf@webshell:~$ cd Addadshashanammu 
luispuentes-picoctf@webshell:~/Addadshashanammu$ ls -la
total 4
drwxr-xr-x 3 luispuentes-picoctf luispuentes-picoctf   28 Mar 16  2021 .
drwxr-xr-x 3 luispuentes-picoctf luispuentes-picoctf 4096 Feb 26 19:00 ..
drwxr-xr-x 3 luispuentes-picoctf luispuentes-picoctf   28 Mar 16  2021 Almurbalarammi
luispuentes-picoctf@webshell:~/Addadshashanammu$ cd Almurbalarammi/
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi$ ls
Ashalmimilkala
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi$ cd Ashalmimilkala/
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala$ ls
Assurnabitashpi
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala$ cd Assurnabitashpi/
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi$ ls
Maelkashishi
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi$ cd Maelkashishi/
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi$ ls
Onnissiralis
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi$ Cd Onnissiralis/
-bash: Cd: command not found
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi$ cd Onnissiralis/
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis$ ls
Ularradallaku
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis$ cd Ularradallaku/
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls -la
total 12
drwxr-xr-x 2 luispuentes-picoctf luispuentes-picoctf   35 Mar 16  2021 .
drwxr-xr-x 3 luispuentes-picoctf luispuentes-picoctf   27 Mar 16  2021 ..
-rwxr-xr-x 1 luispuentes-picoctf luispuentes-picoctf 8320 Mar 16  2021 fang-of-haynekhtnamet
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
luispuentes-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$
```

## Notas


## Referencias