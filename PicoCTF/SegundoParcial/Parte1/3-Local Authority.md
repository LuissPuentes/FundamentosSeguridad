## Objetivo 
Can you get the flag?Go to this [website](http://saturn.picoctf.net:50920/) and see what you can discover.

## Solución
```bash
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

picoCTF{j5_15_7r4n5p4r3n7_05df90c8}
## Notas
Intentamos loggearnos en la pagina, y nos ingresa a una pagina nueva donde el html cambia, en el cual nos aparece un archivo llamado secure.js donde nos da las credenciales de acceso correctas.

## Referencias
https://elcodigoascii.com.ar/