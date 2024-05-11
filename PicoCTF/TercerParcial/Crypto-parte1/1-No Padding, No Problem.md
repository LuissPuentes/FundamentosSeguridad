## Objetivo 
Oracles can be your best friend, they will decrypt anything, except the flag's ciphertext. How will you break it? Connect with `nc mercury.picoctf.net 10333`.

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1]
└─$ nc mercury.picoctf.net 10333
Welcome to the Padding Oracle Challenge
This oracle will take anything you give it and decrypt using RSA. It will not accept the ciphertext with the secret message... Good Luck!


n: 96350952460569164304108647019911634125678626790170811996856194487169013862432459875716930776365890483229756863750428509515459618615847909466440622498201327659883519406630509504334364093859561192889939893075881033405385924922548452911508947415158512204836845931506755111690628378007110476456646991797634125103
e: 65537
ciphertext: 32601033894040792910292570449262759201165676410962072540713209620759866101944129574263738283391981091384996931316915564867850031421366703545124869276034022630572775400907946098215062411752962347270218956801120418868712999494645188658061595865942023239401831267120819299886747205647422873178183210226361733116


Give me ciphertext to decrypt: 1516123200313403191568980804456329377673248551974219788498103256158983241416175065852795355358035347890870247478916380068752310281182882872867551186733166152743214820594764795058669865956688563516468322663245574551159014671463998644688031204127618766983958101384773505667640613960189349276126311029990583843457281831355383244719932905178722153306371709845553811666331610264801289179111450426967338052810054975012795206819463302193756562039430208818302587698443797159456148976268161807283498895017936149128962083787020340789561617415964668827323714889001294257670645442633028581124659143983545920637459802762772797352
Here you go: 580550060391700078946913236734911770139931497702556153513487440893406629034802718534645538074938502890768853279675297196794


┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial3/crypto_parte1]
└─$ python3
Python 3.11.6 (main, Oct  8 2023, 05:06:43) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes>>> e=65537
>>> n=96350952460569164304108647019911634125678626790170811996856194487169013862432459875716930776365890483229756863750428509515459618615847909466440622498201327659883519406630509504334364093859561192889939893075881033405385924922548452911508947415158512204836845931506755111690628378007110476456646991797634125103
>>> c=32601033894040792910292570449262759201165676410962072540713209620759866101944129574263738283391981091384996931316915564867850031421366703545124869276034022630572775400907946098215062411752962347270218956801120418868712999494645188658061595865942023239401831267120819299886747205647422873178183210226361733116
>>> m=pow(2,e,n)*c
>>> m
1516123200313403191568980804456329377673248551974219788498103256158983241416175065852795355358035347890870247478916380068752310281182882872867551186733166152743214820594764795058669865956688563516468322663245574551159014671463998644688031204127618766983958101384773505667640613960189349276126311029990583843457281831355383244719932905178722153306371709845553811666331610264801289179111450426967338052810054975012795206819463302193756562039430208818302587698443797159456148976268161807283498895017936149128962083787020340789561617415964668827323714889001294257670645442633028581124659143983545920637459802762772797352
>>> 
>>> m2=580550060391700078946913236734911770139931497702556153513487440893406629034802718534645538074938502890768853279675297196794
>>> m2//2
290275030195850039473456618367455885069965748851278076756743720446703314517401359267322769037469251445384426639837648598397
>>> long_to_bytes(m2//2)
b'picoCTF{m4yb3_Th0se_m3s54g3s_4r3_difurrent_1772735}'
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

-from Crypto.Util.number import long_to_bytes

m=pow(2,e,n)*c

## Referencias
https://en.wikipedia.org/wiki/RSA_(cryptosystem)