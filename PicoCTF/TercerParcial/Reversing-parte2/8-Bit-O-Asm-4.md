## Objetivo 
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

## Solución
```bash
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-4]
└─$ ls
disassembler-dump0_d.txt
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-4]
└─$ cat disassembler-dump0_d.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-4]
└─$ python3
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> hex(0x2710>=0x9fe1a)
'0x0'
>>> hex(0x9fe1a-0x65)
'0x9fdb5'
>>> ascii(0x9fdb5)
'654773'
>>> 

```

picoCTf{654773}
## Notas
Aquí es revisar solo una comparación donde lo que esta en rbp-0x4 es menor o igual a 0x2710

## Referencias
https://es.wikipedia.org/wiki/NOP
https://sourceware.org/gdb/
https://moisesrbb.tripod.com/unidad5.htm