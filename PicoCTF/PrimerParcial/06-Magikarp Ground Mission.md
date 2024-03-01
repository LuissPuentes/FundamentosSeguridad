## Objetivo 
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `6dee9772`

Additional details will be available after launching your challenge instance.

## Solución
```bash
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ car instructions-to-2of3.txt 
-bash: car: command not found
ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ ^C 
ctf-player@pico-chall$ cd home
ctf-player@pico-chall$ ls
ctf-player
ctf-player@pico-chall$ ls -la
total 16
drwxr-xr-x 1 root       root       4096 Mar 16  2021 .
drwxr-xr-x 1 root       root       4096 Feb 26 19:06 ..
drwxr-xr-x 1 ctf-player ctf-player 4096 Feb 26 19:07 ctf-player
ctf-player@pico-chall$ cd ctf-player/
ctf-player@pico-chall$ ls     
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt 
540e4e79}
ctf-player@pico-chall$
```

picoCTF{xxsh_0ut_0f_\/\/4t3r_540e4e79}
## Notas
con cd .. te mueves una carpeta atras
