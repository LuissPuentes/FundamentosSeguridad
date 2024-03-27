## Objetivo 
Connect to this PostgreSQL server and find the flag!`psql -h saturn.picoctf.net -p 53890 -U postgres pico`Password is `postgres`

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2]
└─$ psql -h saturn.picoctf.net -p 53890 -U postgres pico
Password for user postgres: 
psql (16.1 (Debian 16.1-1), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# 
pico=# 
pico=#
pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 

```


## Notas
con el comando \dt psql nos muestra las tablas existentes en la base de datos

con una consulta simple de la tabla flags, nos muestra la bandera oculta en la direccion de Luke Skywalker

## Referencias
https://www.postgresql.org/docs/current/app-psql.html