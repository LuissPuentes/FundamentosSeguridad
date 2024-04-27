## Objetivo 
What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)

## Solución
```bash
stack

[] <-esp
[] <-ebp-0xc
[-0x1fffffef5 ] <-ebp-0x8
[0x31] <-ebp-0x4
[ebp ] <-ebp
[ret ] <-ebp+0x4
[0xb ] <-ebp+0x8
[0x2e] <-ebp+0xc

registers
[0xb ] eax

asm2: (0xb,0x2e)

        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x509 <asm2+28>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  sub    DWORD PTR [ebp-0x8],0xffffff80
        <+28>:  cmp    DWORD PTR [ebp-0x8],0x63f3
        <+35>:  jle    0x501 <asm2+20>
        <+37>:  mov    eax,DWORD PTR [ebp-0x4]
        <+40>:  leave  
        <+41>:  ret    
```

```
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0xb <=0x63f3
True
>>> hex(0x2e+0x1)
'0x2f'
>>> hex(0xb - 0xffffff80)
'-0xffffff75'
>>> -0xffffff75 <=0x63f3
True
>>> hex(0x2f+0x1)
'0x30'
>>> hex(-0xffffff75 - 0xffffff80 )
'-0x1fffffef5'
>>> -0x1fffffef5 <=0x63f3
True
>>> hex(0x30+0x1)
'0x31'
>>> hex(-0xffffff75 - 0xffffff80 )
'-0x1fffffef5'




Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0xb <=0x63f3
True
>>> hex(0x2e+0x1)
'0x2f'
>>> hex(-128)
'-0x80'
>>> hex(0xb-(-128))
'0x8b'
>>> 0x8b <= 0x63f3
True
>>> hex(0x8b)
'0x8b'
>>> hex(0x8b-0x63f3)
'-0x6368'
>>> hex(0x63f3/0x8b)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'float' object cannot be interpreted as an integer
>>> 0x63f3/0x8b
184.0791366906475
>>> int(0x8b)
139
>>> hex(139+184)
'0x143'
>>> hex(139+185)
'0x144'
>>> hex(0xb-(-0x80))
'0x8b'
>>> hex(0x8b)

```

## Notas
No se puede resolver porque se cicla haca un numero negativo y en la comparacion nunca se permitira que se rompa el ciclo

se intento tomando el valor de 0xffffff80 como -128 o 0x80 y no funciono tampoco

## Referencias
https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm

