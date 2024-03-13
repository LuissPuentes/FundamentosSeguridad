## Objetivo 
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Solución
```bash
┌──(luispuentes㉿kali)-[~/picoctf/forensic/extensions]
└─$ ls
flag.txt

┌──(luispuentes㉿kali)-[~/picoctf/forensic/extensions]
└─$ file flag.txt 
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
┌──(luispuentes㉿kali)-[~/picoctf/forensic/extensions]
└─$ hexeditor flag.txt 

┌──(luispuentes㉿kali)-[~/picoctf/forensic/extensions]
└─$ mv flag.txt flag.png

┌──(luispuentes㉿kali)-[~/picoctf/forensic/extensions]
└─$ open flag.png 

picoCTF{now_you_know_about_extensions}

```


## Notas
se modifico la extension del archivo ya que en el hexedit se comprobo que era un archivo png y no un txt

## Referencias
https://en.wikipedia.org/wiki/File_format
https://en.wikipedia.org/wiki/List_of_file_signatures
