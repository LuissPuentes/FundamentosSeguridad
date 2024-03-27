## Objetivo 
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:56615/) out.

## Solución
```bash
picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}
```

## Notas
como el nombre del reto nos dice, primero se reviso el robots.txt de la pagina,  lo que nos dio algunos codigos que decifrando en cyberchef nos dio: js/myfile.txt

por lo que se cambia en la url robots.txt por js/myfile.txt y nos da la contraseña.

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YW5NdmJYbG1hV3hsTG5SNGRBPT0&ieol=CRLF&oeol=VT