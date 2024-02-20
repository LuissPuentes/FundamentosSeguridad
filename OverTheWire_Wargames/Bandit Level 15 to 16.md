## Objetivo 
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Datos de acceso
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
## Solución
```bash
bandit15@bandit:~$ openssl s_client -conect localhost:30001
s_client: Unknown option: -conect
s_client: Use -help for summary.
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 13:33:06 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 20 13:33:06 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 20 13:32:06 2024 GMT; NotAfter: Feb 20 13:33:06 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEbT0xEzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTMzMjA2WhcNMjQwMjIwMTMzMzA2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCk
6f42mpnxjjpCqtrhC+dM4zGlIMRdgyQqPp+tEGl9BT1mC7b8tyj8oup/qOR4P0Qh
BucxH8Sdm9oNZzeDS2REvCXRTtY38vMXhSRM6I+YGIG0DO6+9e4ky0wBVcqv12Ws
GNcV4+t+Ti/mK0MFUPKwHwLM5+NfSWnvS3dy76La1GUS47xebOtuS5Nx/Uw5Nifq
M0fLPAc5yVmV2E2aQ38puU2MvmVLsqaywfWlRc5Wx2hRov9InJcB+P7cA0wQ1Zjx
GEJlSH7rqfH5D3xATVhDFvbuqRPp77SowBRfE5aaaVAeA7USt33t/mjcRzf9n9JF
y4KH1k2iO8QrwS56zaX7AgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAN
c04815J6jgxj07alVV+Oa7SL0rl84/3Z5VF5Ih6jaESe9Vb7yh5o86RkY5d3mieD
GoBzwbv9fBso3YDppoPV/22fKXVEmoGpac770TXoMYvsMOaWQxS33tjiGe7Q7sGG
kW64pCqgJV4L8si2F5Y4ucgWu/bswXsix3uEEitctdgbvIJn9GeNOtsJ2KRmn6fT
zx3dEq0Qsy1dmWJxggRpiuYNgKzxgTjz7Msoo+1sLFvXy6wl4AD+oqKMMC5yxKOq
D0rpPbyeTWpDzEwTNQpTFBcwcS/M808q8o3viuC7D2j4vRnlqVMO7vUkjLAA0hlH
/Yw1vSvIdM86o5jquej7
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
    Session-ID: 22F9FD5FFADF5FA4798E209098501F3709F00A5967D412AE025F658E4ADC33D3
    Session-ID-ctx:
    Resumption PSK: BB4719E268E94C2BFC10AACA6542CAE3B57FAA6C3DF9B8E47864639053DA69E93E58CB537533A94E077EB4EDBF5D5E20
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 4d 6e 1d 99 be 58 0d be-d1 96 d1 f0 fe c2 b9 53   Mn...X.........S
    0010 - 1e a2 3c 30 ab 77 f2 ec-03 ec 08 50 09 93 17 5e   ..<0.w.....P...^
    0020 - 03 ad 00 bf 85 38 e6 b5-49 0a 15 07 3b fa fe 21   .....8..I...;..!
    0030 - b5 24 f9 dc 82 59 ba e0-6f e8 f5 5b eb 7b fb e0   .$...Y..o..[.{..
    0040 - 22 f2 c2 0d 18 77 ba a5-65 c5 b5 1b b6 21 80 d3   "....w..e....!..
    0050 - be 64 48 49 fb 9f f4 5b-ee ea 85 f6 4b a6 2f a0   .dHI...[....K./.
    0060 - 22 d4 8e b3 b0 a8 18 b9-a1 62 c7 74 ad d3 8c f9   "........b.t....
    0070 - ee 0c b6 5e 46 49 e2 05-e5 fd fc b2 82 60 6e 02   ...^FI.......`n.
    0080 - 93 ab b4 a6 20 6d 32 a9-12 cf 31 21 cd c5 15 84   .... m2...1!....
    0090 - 6f 08 db 85 02 2f 0d f7-8d c4 08 3d 4f 60 2a 19   o..../.....=O`*.
    00a0 - 85 a8 d7 6b d6 8e 4a 89-f6 e7 85 d1 5a 75 cf 8f   ...k..J.....Zu..
    00b0 - dc 47 01 4c a0 79 14 a7-7e 3b 34 fa 1e 85 1d 1d   .G.L.y..~;4.....
    00c0 - bc f6 9f b0 5f 10 c5 4b-0e 36 94 19 e5 9c 1d 89   ...._..K.6......

    Start Time: 1708448139
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
    Session-ID: FAACE17EB8F5B448657D45974DD7F47C4AF54A07853586263969A3F9266DE2CD
    Session-ID-ctx:
    Resumption PSK: 300B440DB088AD98C4065FCEF951209B555BFF273D7EC71F02FFAE0C9FA6AA7FF853EFA85064DA27200C839E2110F050
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 4d 6e 1d 99 be 58 0d be-d1 96 d1 f0 fe c2 b9 53   Mn...X.........S
    0010 - 6f b8 52 69 de 7a 2a 27-d9 79 91 1e 92 ee 0b e4   o.Ri.z*'.y......
    0020 - 35 d7 81 16 f2 07 37 90-d3 98 59 30 36 0a 4d 71   5.....7...Y06.Mq
    0030 - db e3 62 55 db fa a2 ba-8d 38 b8 cb 3d 69 ac a1   ..bU.....8..=i..
    0040 - 0d 42 8d 04 18 3c 5a d7-74 87 60 02 51 27 5f 33   .B...<Z.t.`.Q'_3
    0050 - 91 06 2d 7a c8 7e 0f 31-b2 3e 5a 38 fb 12 98 14   ..-z.~.1.>Z8....
    0060 - d0 07 c3 18 d0 c3 4e f9-99 e4 f9 ad 85 6c 9d e1   ......N......l..
    0070 - 3a 57 1c d6 8b ad 0a 71-45 f9 d1 68 d6 4d 8b f7   :W.....qE..h.M..
    0080 - f6 d2 77 f6 8c e1 bc 7f-99 07 51 be 20 f3 dc 31   ..w.......Q. ..1
    0090 - 23 5a 24 f9 cd 62 8a ff-64 f6 a0 db f2 6a 8c e5   #Z$..b..d....j..
    00a0 - a6 f3 9b 51 d4 ad 35 19-cd 25 46 a5 80 94 ff c0   ...Q..5..%F.....
    00b0 - 99 50 82 b3 13 5d c2 96-cc 6e 5c 6d bd 82 4f f7   .P...]...n\m..O.
    00c0 - e8 fb 74 ba 3f 31 0b fd-57 16 a2 3f cc 66 f6 99   ..t.?1..W..?.f..

    Start Time: 1708448139
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$
```

## Notas
- Se utiliza el comando `openssl s_client` para establecer una conexión SSL con el servidor. 

## Referencias
- [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Secure_Socket_Layer)
- [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)
