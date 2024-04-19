## Objetivo 
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/mindpsqs]
└─$ ls
values
                                                                                                                                                                      
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/mindpsqs]
└─$ cat values    
Decrypt my super sick RSA:
c: 421345306292040663864066688931456845278496274597031632020995583473619804626233684
n: 631371953793368771804570727896887140714495090919073481680274581226742748040342637
e: 65537                                                                                                                                                                      
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/mindpsqs]
└─$ python3
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c=421345306292040663864066688931456845278496274597031632020995583473619804626233684
>>> n=631371953793368771804570727896887140714495090919073481680274581226742748040342637
>>> e=65537
>>> p=1461849912200000206276283741896701133693
>>> q=431899300006243611356963607089521499045809
>>> n = p * q
>>> n
631371953793368771804570727896887140714495090919073481680274581226742748040342637
>>> tn = (p-1) * (q-1)
>>> d=inverse(e,tn)
>>> pow(c,d,n)
13016382529449106065927291425342535437996222135352905256639647889241102700065917
>>> long_to_bytes(pow(c,d,n))
b'picoCTF{sma11_N_n0_g0od_55304594}'
>>>
```

## Notas
RSA
c - texto cifrado
m - mensaje texto plano
p - primo 1
q - primo 2
n - modulo
tn - totinet n (euler)
e - exponente (llave publica) 2^16+1 = 65537
d - llave privada

n = p * q
tn = (p-1) * (q-1)
d = e mod inv tn / inverse (e,tn)

Encriptar       : c = m^e mod n / pow(m,e,n)
Desencriptar : m= c^d mod n / pow(c,d,n)

-from Crypto.Util.number import inverse
-from Crypto.Util.number import long_to_bytes

 - En la pagina factordb se factorizo el numero n para obtener p y q y poder descifrar el mensaje.
 - Otra manera de resolverlo es con la herramienta RsaCtfTool que nos ayuda a decifrar rsa mas facil.
## Referencias
http://factordb.com/index.php?query=631371953793368771804570727896887140714495090919073481680274581226742748040342637

https://github.com/RsaCtfTool/RsaCtfTool