## Objetivo 
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/9670/` ([link](https://jupiter.challenges.picoctf.org/problem/9670/)) or http://jupiter.challenges.picoctf.org:9670 

## Solución

```bash
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}
```

## Notas
al abrir la pagina web en otra pestaña y analizar el codigo fuente podemos ver la primera parte de la contraseña
picoCTF{tru3_d3

Despues en ese mismo html vemos el acceso al archivo de estilos, donde encontramos la segunda parte de la bandera
t3ct1ve_0r_ju5t

Despues en ese mismo html vemos el acceso al archivo de javascript, donde encontramos la tercera parte de la bandera
_lucky?2e7b23e3}

## Referencias
https://jupiter.challenges.picoctf.org/problem/9670/