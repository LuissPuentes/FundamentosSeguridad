## Objetivo 
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm) has extraordinarily helpful information...
## Solución
```bash
luispuentes-picoctf@webshell:~$ chmod +x warm
luispuentes-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
luispuentes-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
luispuentes-picoctf@webshell:~$ 
```
## Notas
con chmod +x .- da permisos de ejecucion para un programa en linux