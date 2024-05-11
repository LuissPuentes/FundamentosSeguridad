## Objetivo 
Can you figure out what is in the eax register? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}.
Download the assembly dump here.

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-2]
└─$ ls
disassembler-dump0_b.txt
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-2]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-2]
└─$ python3                                               
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii(0x9fe1a)
'654874'
>>> 

```

picoCTF{654874}
## Notas
se le asigna a eax, el valor en rpb-0x4 que una instruccion arriba nos dice que es 0x9fe1a

## Referencias
https://es.wikipedia.org/wiki/NOP
https://sourceware.org/gdb/