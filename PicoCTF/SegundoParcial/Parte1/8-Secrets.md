## Objetivo 
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:64727/).

## Solución
```bash
|   |
|---|
|<html>|
||<head>|
||<title></title>|
||<link rel="stylesheet" href="[mycss.css](http://saturn.picoctf.net:64727/secret/hidden/superhidden/mycss.css)" />|
||</head>|
|||
||<body>|
||<h1>Finally. You found me. But can you see me</h1>|
||<h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_790d2615}</h3>|
||</body>|
||</html>|
```

picoCTF{succ3ss_@h3n1c@10n_790d2615}
## Notas
se inspecciona la pagina y hay un archivo en un directorio llamado secret, por lo que se ingresa a la liga view-source:http://saturn.picoctf.net:64727/secret/
y ahi inspeccionando la pagina hay otro directorio llamado hidden, por lo que se ingresa a la liga 
view-source:http://saturn.picoctf.net:64727/secret/hidden/
donde hay un ultimo directorio llamado superhidden donde inspeccionando la pagina nos entrega la solucion ya que en esa pagina nos dice Finally. You found me. But can you see me, ya que la bandera estaba del mismo color que el fondo.
