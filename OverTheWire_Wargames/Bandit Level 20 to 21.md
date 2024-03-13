## Objetivo 
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

## Datos de acceso
bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
## Solución
```bash
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15600 Oct  5 06:19 suconnect
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ nc -lnvp 69420 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 3064874
bandit20@bandit:~$ Listening on 0.0.0.0 3884
jobs
[1]+  Running                 nc -lnvp 69420 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$ jobs
[1]+  Running                 nc -lnvp 69420 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$ ^C
bandit20@bandit:~$ jobs
[1]+  Running                 nc -lnvp 69420 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
bandit20@bandit:~$
bandit20@bandit:~$ ./subconect 3884
-bash: ./subconect: No such file or directory
bandit20@bandit:~$ ./subconect 69420
-bash: ./subconect: No such file or directory
bandit20@bandit:~$ ./suconect 69420
-bash: ./suconect: No such file or directory
bandit20@bandit:~$ ./suconnect 3884
Connection received on 127.0.0.1 50666
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -lnvp 69420 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$
```

## Notas
tmux abre una terminal virutal
	ctrl + b comandos "(nueva term), %, space(cambia horizontal y vertical), flechas(moverse entre terminales)
		ctrl + b : setw -g mouse on
## Referencias

https://www.ionos.mx/digitalguide/servidores/know-how/tmux-multiplexor-de-terminal/