## Objetivo 
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng).

## Solución
```bash
picoCTF{p33kab00_1_s33_u_deadbeef}
```


## Notas
Al analizar el paquete con wireshark comenzamos a seguir los tcp streams, no se encuentra como tal por la palabra pico, pero en el stream 5 encontramos cvpbPGS{c33xno00_1_f33_h_qrnqorrs} que tiene un formato similar al de la bandera, al aplicarle rot13 nos da la bandera que necesitamos.

## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=Y3ZwYlBHU3tjMzN4bm8wMF8xX2YzM19oX3FybnFvcnJzfQ&ieol=CRLF&oeol=CR