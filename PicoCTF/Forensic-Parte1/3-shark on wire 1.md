## Objetivo 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Solución
```bash
┌──(luispuentes㉿kali)-[~/picoctf/forensic/sharkonwire1]
└─$ ls
capture.pcap

┌──(luispuentes㉿kali)-[~/picoctf/forensic/sharkonwire1]
└─$ wireshark capture.pcap 

picoCTF{StaT31355_636f6e6e}
```


## Notas
Wireshark nos permite analizar paquetes en la red

con el filtro udp.stream eq 6 nos encontramos con el paquete UDP que contenia la contraseña

## Referencias
https://www.solarwinds.com/resources/it-glossary/pcap