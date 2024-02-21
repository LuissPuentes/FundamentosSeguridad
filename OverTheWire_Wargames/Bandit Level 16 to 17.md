## Objetivo 
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Datos de acceso
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solución
``

``` bash
bandit16@bandit:~$ nmap 127.0.0.1
Starting Nmap 7.80 ( https://nmap.org ) at 2024-02-21 18:09 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00013s latency).
Not shown: 994 closed ports
PORT      STATE SERVICE
22/tcp    open  ssh
1111/tcp  open  lmsocialserver
1840/tcp  open  netopia-vo2
4321/tcp  open  rwhois
8000/tcp  open  http-alt
30000/tcp open  ndmps

Nmap done: 1 IP address (1 host up) scanned in 0.10 seconds
bandit16@bandit:~$ nmap 127.0.0.1 -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2024-02-21 18:10 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00010s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.06 seconds
bandit16@bandit:~$ which nmap
/usr/bin/nmap
bandit16@bandit:~$ which nc
/usr/bin/nc
bandit16@bandit:~$ nc -vz localhost 31000-32000 2>&1 | grep succ
Connection to localhost (127.0.0.1) 31046 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31518 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31691 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31790 port [tcp/*] succeeded!
Connection to localhost (127.0.0.1) 31960 port [tcp/*] succeeded!
bandit16@bandit:~$



bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 20 17:50:06 2024 GMT; NotAfter: Feb 20 17:51:06 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEQ9wEgDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTc1MDA2WhcNMjQwMjIwMTc1MTA2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDA
gdd50zQdwKnADuCYAoUSFvGreD2Mr/e6QZK+31XsKXCd/+cGHdmkqerggVlwno8T
3lmAaRw+Pk/nNdn3xJEGGq5guV2YhAnT+IQgP6+76ii/4gUCQxnaTtmslJDSfv7i
km+qYsFRL1YdtOo5od2etkLdorXGqGcIrB6ilCgKgQ2Q7FqMjh7n37HPk8yaWCwX
M/JZ7jkXw4mf2Un9UILgo/oJfR0JhMq6cDkHztG0E6j5ruknDeeOMGimH9pmzaa9
xdJe1GTtk+v03FIng0IfHi0HVPUCN8dl9rKLzn/LKZ3UftyffIErE7nDCLaGpVBK
DQzkq5gMPShGa1RT7nkFAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBh
XmVUELbEPhoHaMrhwHyd24bRzYiiOemi75OA6QywOLh7moC8MGKvtI0mHhhA+lfB
eEvOOPwL5om4culG+KnC24fdWzwX/PPtkYKocNSrIQINrVhTwBbGwnC+WCSYizZS
43Zav+szrJ6H66qO4x4wXU9p1qC24dIpY5dfBsy4m8P/XzUtg68YJng1EIuGM6DF
CnMWXUB0cfUgBsbWPMrQlJd5sHifKeglK3kBCXn3zb9T881YbLNAwMK2a5SnPdh8
eTg1e7pdNYwPvHcxYPySGyQCkLpLHduWUxVNrUfsVHrxI6rrHynZ5vv4+ulAmhAc
YoU33/wx/D1oycw1GLHh
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 4D6F3654FA2CCA81F7E0525327BE312D20E21F50D0D717236C8821757C9036A3
    Session-ID-ctx:
    Resumption PSK: B5F422088CBB33961123B14C84BB2664FC65474871717FB1AC3A2718D343842AF893381648423C7D2FF7762450DD7C67
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 92 ed 0d d5 75 f9 0c 95-ed 08 73 73 af f3 6c c3   ....u.....ss..l.
    0010 - 9f 1b 85 c6 a5 03 3e 1f-cc b3 30 66 a5 9f 25 75   ......>...0f..%u
    0020 - 57 c1 c7 1e e4 b4 be fd-d8 4f d5 a3 1a 40 e5 a6   W........O...@..
    0030 - 80 60 ed e3 00 ca 08 64-b9 42 d4 37 f7 6b 42 58   .`.....d.B.7.kBX
    0040 - ff 62 1c 41 5c 96 78 31-b8 b9 df d3 33 1a 79 e0   .b.A\.x1....3.y.
    0050 - b1 fd 99 e3 a9 5b f8 f1-72 f4 15 a7 07 93 8b 69   .....[..r......i
    0060 - e8 53 0c 2e c4 84 a2 64-43 c6 44 b8 c3 b6 9b c1   .S.....dC.D.....
    0070 - e3 fa 58 98 d8 41 aa c9-d9 cc 82 70 96 6d 60 49   ..X..A.....p.m`I
    0080 - 4e da 01 db 0d 4a c6 d6-e7 ed 60 6d f4 b2 5e b5   N....J....`m..^.
    0090 - a5 80 83 1d 61 b0 2d cc-17 2e 12 e2 0c bf dd 5f   ....a.-........_
    00a0 - ce 08 ca 8c 02 d5 9a 50-54 3a e6 d5 26 0b 5f 5d   .......PT:..&._]
    00b0 - a1 8b 4a 04 de 50 4a 0c-7c 12 6f 1f 63 0f 1d 41   ..J..PJ.|.o.c..A
    00c0 - dc 5a 11 f9 dc 57 99 e2-e4 c1 8e 37 39 f0 79 c8   .Z...W.....79.y.

    Start Time: 1708539440
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 4CE33C7F0980D85801B9F85E9F381CDC43544B75588873C0B85F83481F12345F
    Session-ID-ctx:
    Resumption PSK: CC786137498FADA3A0268D0101A0FF7A671EBE4DC071905CB257CCE2B74ADBBA84BD6EB528231C5E140DAADD1DBE6A96
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 92 ed 0d d5 75 f9 0c 95-ed 08 73 73 af f3 6c c3   ....u.....ss..l.
    0010 - 04 34 64 a7 ed a4 89 59-4d 19 eb 9a f9 6b 8d 45   .4d....YM....k.E
    0020 - a9 2e 68 88 0c 44 38 ef-ec 90 d9 ec 57 8b 01 ba   ..h..D8.....W...
    0030 - f3 57 e7 f8 b2 89 ce 19-b2 a4 db 5b 81 06 24 9d   .W.........[..$.
    0040 - e3 62 a6 19 60 4e 37 62-01 c5 2a df 68 90 d0 c8   .b..`N7b..*.h...
    0050 - 5e a6 a7 04 df fe 65 d1-10 7b bc 4d e9 17 66 8b   ^.....e..{.M..f.
    0060 - 04 0d 62 a5 80 17 c8 05-74 e5 19 04 18 4a 79 74   ..b.....t....Jyt
    0070 - 79 9d 4d 27 42 e0 9f 2f-bf e0 5c 0b 58 d6 6b 2e   y.M'B../..\.X.k.
    0080 - 93 95 52 e2 fc b6 7e dc-d3 20 0b 19 d2 3e ea 23   ..R...~.. ...>.#
    0090 - c3 f8 54 f8 99 ca 99 f5-35 3a b7 57 93 8a 9e d5   ..T.....5:.W....
    00a0 - 31 32 43 62 0c 48 78 dd-4a df cf 1d ff 5f 2f 01   12Cb.Hx.J...._/.
    00b0 - 92 9c 7d af 87 bb 10 08-b0 31 dd 87 66 2f 0c 14   ..}......1..f/..
    00c0 - f8 47 50 4a 86 6d dd f7-42 91 91 6f 40 d5 2c 2a   .GPJ.m..B..o@.,*

    Start Time: 1708539440
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
```

## Notas
nc - para cuando no esta nmap
nmap - para revisar puertos libres
nano para crear un archivo
chmod 600 LaLlave - para darle permisos que solo yo pueda leero o modificarlo
ls -la -- para ver que propiedades tiene un archivo

## Referencias
[Port scanner on Wikipedia](https://en.wikipedia.org/wiki/Port_scanner)
