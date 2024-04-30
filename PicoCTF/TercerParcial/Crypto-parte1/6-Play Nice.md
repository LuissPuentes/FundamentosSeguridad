## Objetivo 
Not all ancient ciphers were so bad... The flag is not in standard format. `nc mercury.picoctf.net 40742` [playfair.py](https://mercury.picoctf.net/static/283dcc58048f3a6ac83b4c11ec696954/playfair.py)

## Solución
```bash
                                                                                  
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/PlayNice]
└─$ ls
playfair.py
                                                                                  
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/PlayNice]
└─$ cat playfair.py 
#!/usr/bin/python3 -u
import signal

SQUARE_SIZE = 6


def generate_square(alphabet):
        assert len(alphabet) == pow(SQUARE_SIZE, 2)
        matrix = []
        for i, letter in enumerate(alphabet):
                if i % SQUARE_SIZE == 0:
                        row = []
                row.append(letter)
                if i % SQUARE_SIZE == (SQUARE_SIZE - 1):
                        matrix.append(row)
        return matrix

def get_index(letter, matrix):
        for row in range(SQUARE_SIZE):
                for col in range(SQUARE_SIZE):
                        if matrix[row][col] == letter:
                                return (row, col)
        print("letter not found in matrix.")
        exit()

def encrypt_pair(pair, matrix):
        p1 = get_index(pair[0], matrix)
        p2 = get_index(pair[1], matrix)

        if p1[0] == p2[0]:
                return matrix[p1[0]][(p1[1] + 1)  % SQUARE_SIZE] + matrix[p2[0]][(p2[1] + 1)  % SQUARE_SIZE]
        elif p1[1] == p2[1]:
                return matrix[(p1[0] + 1)  % SQUARE_SIZE][p1[1]] + matrix[(p2[0] + 1)  % SQUARE_SIZE][p2[1]]
        else:
                return matrix[p1[0]][p2[1]] + matrix[p2[0]][p1[1]]

def encrypt_string(s, matrix):
        result = ""
        if len(s) % 2 == 0:
                plain = s
        else:
                plain = s + "irlgektq8ayfp5zu037nov1m9xbc64shwjd2"[0]
        for i in range(0, len(plain), 2):
                result += encrypt_pair(plain[i:i + 2], matrix)
        return result

alphabet = open("key").read().rstrip()
m = generate_square(alphabet)
msg = open("msg").read().rstrip()
enc_msg = encrypt_string(msg, m)
print("Here is the alphabet: {}\nHere is the encrypted message: {}".format(alphabet, enc_msg))
signal.alarm(18)
resp = input("What is the plaintext message? ").rstrip()
if resp and resp == msg:
        print("Congratulations! Here's the flag: {}".format(open("flag").read()))

# https://en.wikipedia.org/wiki/Playfair_cipher


┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/PlayNice]
└─$ nc mercury.picoctf.net 40742
Here is the alphabet: irlgektq8ayfp5zu037nov1m9xbc64shwjd2
Here is the encrypted message: h5a1sqeusdi38obzy0j5h3ift7s2r2
What is the plaintext message?

┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/PlayNice]
└─$ python3
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> m="XQYVHTG02JKPLZO8EYHU25KTIP2DKH"
>>> m.lower()
'xqyvhtg02jkplzo8eyhu25ktip2dkh'
>>> 
zsh: suspended  python3
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/PlayNice]
└─$ nc mercury.picoctf.net 40742                        
Here is the alphabet: irlgektq8ayfp5zu037nov1m9xbc64shwjd2
Here is the encrypted message: h5a1sqeusdi38obzy0j5h3ift7s2r2
What is the plaintext message? xqyvhtg02jkplzo8eyhu25ktip2dkh
Congratulations! Here's the flag: 25a0ea7ff711f17bddefe26a6354b2f3
                                                                                                                                                                       
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1/PlayNice]
└─$ 



```


## Notas
En la pagina https://www.dcode.fr/playfair-cipher deciframos el texto para reenviarlo, y nos regrese el valor de la bandera.

## Referencias
https://en.wikipedia.org/wiki/Playfair_cipher

https://www.dcode.fr/playfair-cipher