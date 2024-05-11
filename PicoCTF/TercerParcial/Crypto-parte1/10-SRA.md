## Objetivo 
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...Connect to the program on our server: `nc saturn.picoctf.net 61252`Download the program: [chal.py](https://artifacts.picoctf.net/c/296/chal.py)

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/RSA]
└─$ ls
chal.py
                                                                                                                                                                      
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/RSA]
└─$ cat chal.py    
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

pride = "".join(choice(ascii_letters + digits) for _ in range(16))
gluttony = getPrime(128)
greed = getPrime(128)
lust = gluttony * greed
sloth = 65537
envy = inverse(sloth, (gluttony - 1) * (greed - 1))

anger = pow(bytes_to_long(pride.encode()), sloth, lust)

print(f"{anger = }")
print(f"{envy = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == pride:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")


┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/RSA]
└─$ python3 sra.py 
[+] Opening connection to saturn.picoctf.net on port 61252: Done
/home/luispuentes/picoCTF/Parcial3/crypto_parte1/RSA/sra.py:20: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/luispuentes/picoCTF/Parcial3/crypto_parte1/RSA/sra.py:23: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 59027924105091150455781417599574944340088707956895616681764108766950190413359
d= 44320779460360441512239314689661298552511155778202525168602081898054205041793
/home/luispuentes/picoCTF/Parcial3/crypto_parte1/RSA/sra.py:27: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Dame los divisores de  2904650923493642255387627966816332523235923616236058891974674641352778435823987840
[2, 2, 2, 2, 2, 2, 2, 3, 3, 3, 3, 5, 17, 37, 463, 1181, 10789, 251071, 23750291, 469752391485047527, 5390533380249955956495368025519181]
{257520708688212815552366030943311165761, 261113558143276546701475367490437805121, 203438729770633337798135189283093890941, 330840849322036438886845016613851754457}
ml9ZTKxFt5ZjBHDB
/home/luispuentes/picoCTF/Parcial3/crypto_parte1/RSA/sra.py:54: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> ml9ZTKxFt5ZjBHDB\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_dd808298}\r\n'
ml9ZTKxFt5ZjBHDB
[*] Closed connection to saturn.picoctf.net port 61252
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/RSA]
└─$nano sra.py


```

```
from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

def sub_lists (l):
    comb = []

    for i in range(1,len(l)+1):
        comb += [list(j) for j in combinations(l, i)]
    return comb

def divisors(phi):
   print("Dame los divisores de ", phi-1)
   return(eval(input()))


r = remote('saturn.picoctf.net', 61252)

r.recvuntil("anger =")
ciphertext=int(r.recvline())

r.recvuntil("envy =")
d=int(r.recvline())
print("cipher=",ciphertext)
print("d=",d)
print(r.recvuntil("vainglory?"))
r.recvline()

factors=divisors(d*65537)
combos = sub_lists(factors)
primes = set()

for l in combos:
   product = 1
   
   for k in l:
      product = product * k
   
   if product.bit_length()==128 and primefac.isprime(product+1):
      primes.add(product+1)
print(primes)
primelist = list(primes)

for p in primelist:
   for q in primelist:
      n=p*q

      plain = pow(ciphertext,d,n)
      try:
         plaintext = long_to_bytes(plain)
                  print(plaintext.decode())
         r.sendline(plaintext.decode())
         print(r.recvline())
         print(r.recvline())
         print(r.recvline())
      except:
         continue

```
## Notas
-from gmpy2 import *
-from Crypto.Util.number import long_to_bytes

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

envy = d
e = 65537
Anger =  c
## Referencias
https://es.wikipedia.org/wiki/RSA
https://www.dcode.fr/prime-factors-decomposition