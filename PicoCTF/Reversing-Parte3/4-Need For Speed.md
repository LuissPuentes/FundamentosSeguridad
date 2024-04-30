## Objetivo 
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed).

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/needforspeed]
└─$ cp need-for-speed cracked


──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/needforspeed]
└─$ ls
cracked  need-for-speed
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/needforspeed]
└─$ hexeditor cracked       

┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/needforspeed]
└─$ ./cracked                
Keep this thing over 50 mph!
============================

Creating key...
Finished
Printing flag:
PICOCTF{Good job keeping bus #190ca38b speeding along!}

```

```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/reversing/needforspeed]
└─$ gdb -q need-for-speed
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb) run
Starting program: /home/luispuentes/picoCTF/reversing/needforspeed/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================

Creating key...
Not fast enough. BOOM!
[Inferior 1 (process 56988) exited normally]
(gdb) disassemble main
Dump of assembler code for function main:
   0x000055555540091a <+0>:     push   rbp
   0x000055555540091b <+1>:     mov    rbp,rsp
   0x000055555540091e <+4>:     sub    rsp,0x10
   0x0000555555400922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000555555400925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000555555400929 <+15>:    mov    eax,0x0
   0x000055555540092e <+20>:    call   0x5555554008d8 <header>
   0x0000555555400933 <+25>:    mov    eax,0x0
   0x0000555555400938 <+30>:    call   0x55555540082f <set_timer>
   0x000055555540093d <+35>:    mov    eax,0x0
   0x0000555555400942 <+40>:    call   0x55555540087d <get_key>
   0x0000555555400947 <+45>:    mov    eax,0x0
   0x000055555540094c <+50>:    call   0x5555554008ac <print_flag>
   0x0000555555400951 <+55>:    mov    eax,0x0
   0x0000555555400956 <+60>:    leave
   0x0000555555400957 <+61>:    ret
End of assembler dump.
(gdb) break *(main+30)
Breakpoint 1 at 0x555555400938
(gdb) run
Starting program: /home/luispuentes/picoCTF/reversing/needforspeed/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================


Breakpoint 1, 0x0000555555400938 in main ()
(gdb) jump *(main+35)
Continuing at 0x55555540093d.
Creating key...
Finished
Printing flag:
PICOCTF{Good job keeping bus #190ca38b speeding along!}
[Inferior 1 (process 57469) exited normally]
(gdb) info break
Num     Type           Disp Enb Address            What
1       breakpoint     keep y   0x0000555555400938 <main+30>
        breakpoint already hit 1 time
(gdb)
```
## Notas
GBD
gdb -q need-for-speed
disassemble main
run

break *(main+30)
run
jump *(main+35)

break *(main+30)
call (int) get_key()
call (int) print_flag()

se modifico el hexedit para quitar un timer que cicla el programa, en la linea 938 se colocan 5 90s, para indicar que no realize esa instruccion
## Referencias
https://es.wikipedia.org/wiki/NOP
https://sourceware.org/gdb/