## Objetivo 
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

## Solución
```bash
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-3]
└─$ ls
disassembler-dump0_c.txt
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-3]
└─$ cat disassembler-dump0_c.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-3]
└─$ 
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/Reversing_parte2/Bit-O-Asm-3]
└─$ python3
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> eax=0x9fe1a
>>> hex(0x9fe1a*0x4)
'0x27f868'
>>> hex(0x27f868+0x1f5)
'0x27fa5d'
>>> ascii(0x27fa5d)
'2619997'
>>> 

```

picoCTF{2619997}
## Notas
se realizan las operaciones en python y se obtiene el numero buscado

## Referencias
https://moisesrbb.tripod.com/unidad4.htm
https://es.wikipedia.org/wiki/NOP
https://sourceware.org/gdb/