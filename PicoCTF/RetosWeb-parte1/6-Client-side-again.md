## Objetivo 
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/60786/` ([link](https://jupiter.challenges.picoctf.org/problem/60786/)) or http://jupiter.challenges.picoctf.org:60786

Pista: What is obfuscation?
## Solución
```bash
var _0x5a46 = ["f49bf}", "_again_e", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];

A[8]+A[9]+A[1]+A[0]
'picoCTF{not_this_again_ef49bf}'
```

## Notas
el script en el html se desofusco en jsnice
se saco una variable con partes de la llave
se analizo la posible contraseña
se probo y era correcta
## Referencias
https://www.preemptive.com/what-is-obfuscation/
http://jsnice.org/
