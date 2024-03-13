## Objetivo 
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Solución
```bash
00000000  89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  49 48 44 52                                                                                          .PNG........IHDR
00000010  00 00 06 6A  00 00 04 47   08 02 00 00  00 7C 8B AB                                                                                          ...j...G.....|..
00000020  78 00 00 00  01 73 52 47   42 00 AE CE  1C E9 00 00                                                                                          x....sRGB.......
00000030  00 04 67 41  4D 41 00 00   B1 8F 0B FC  61 05 00 00                                                                                          ..gAMA......a...
00000040  00 09 70 48  59 73 00 00   16 25 00 00  16 25 01 49                                                                                          ..pHYs...%...%.I
00000050  52 24 F0 00  00 FF A5 49   44 41 54 78  5E EC BD 3F                                                                                          R$.....IDATx^..?
00000060  8E 64 CD 71  BD 2D 8B 20   20 80 90 41  83 02 08 D0                                                                                          .d.q.-.  ..A....
00000070  F9 ED 40 A0  F3 6E 40 7B   90 23 8F 1E  D7 20 8B 3E                                                                                          ..@..n@{.#... .>
00000080  B7 C1 0D 70  03 74 B5 03   AE 41 6B F8  BE A8 FB DC                                                                                          ...p.t...Ak.....
00000090  3E 7D 2A 22  33 6F DE 5B   55 DD 3D 3D  F9 20 91 88                                                                                          >}*"3o.[U.==. ..
000000A0  38 71 22 32  EB 4F 57 CF   14 E6 25 FF  E5 FF 5B 2C                                                                                          8q"2.OW...%...[,
000000B0  16 8B C5 62  B1 58 2C 16   8B C5 62 B1  58 2C 16 1D                                                                                          ...b.X,...b.X,..
000000C0  D6 D7 67 8B  C5 62 B1 58   2C 16 8B C5  62 B1 58 2C                                                                                          ..g..b.X,...b.X,
000000D0  16 8B 45 97  F5 F5 D9 62   B1 58 2C 16  8B C5 62 B1                                                                                          ..E....b.X,...b.
000000E0  58 2C 16 8B  C5 62 D1 65   7D 7D B6 58  2C 16 8B C5                                                                                          X,...b.e}}.X,...
000000F0  62 B1 58 2C  16 8B C5 62   B1 58 74 59  5F 9F 2D 16                                                                                          b.X,...b.XtY_.-.
00000100  8B C5 62 B1  58 2C 16 8B   C5 62 B1 58  2C 16 5D D6                                                                                          ..b.X,...b.X,.].
00000110  D7 67 8B C5  62 B1 58 2C   16 8B C5 62  B1 58 2C 16                                                                                          .g..b.X,...b.X,.
00000120  8B 45 97 F5  F5 D9 62 B1   58 2C 16 8B  C5 62 B1 58                                                                                          .E....b.X,...b.X
00000130  2C 16 8B C5  62 D1 65 7D   7D B6 58 2C  16 8B C5 62                                                                                          ,...b.e}}.X,...b
00000140  B1 58 2C 16  8B C5 62 B1   58 74 59 5F  9F 2D 16 8B                                                                                          .X,...b.XtY_.-..
00000150  C5 62 B1 58  2C 16 8B C5   62 B1 58 2C  16 5D D6 D7                                                                                          .b.X,...b.X,.]..
00000160  67 8B C5 62  B1 58 2C 16   8B C5 62 B1  58 2C 16 8B                                                                                          g..b.X,...b.X,..
00000170  45 97 F5 F5  D9 62 B1 58   2C 16 8B C5  62 B1 58 2C                                                                                          E....b.X,...b.X,
00000180  16 8B C5 62  D1 65 7D 7D   B6 58 2C 16  8B C5 62 B1                                                                                          ...b.e}}.X,...b.
00000190  58 2C 16 8B  C5 62 B1 58   74 59 5F 9F  2D 16 8B C5                                                                                          X,...b.XtY_.-...
000001A0  62 B1 58 2C  16 8B C5 62   B1 58 2C 16  5D D6 D7 67                                                                                          b.X,...b.X,.]..g
000001B0  8B C5 62 B1  58 2C 16 8B   C5 62 B1 58  2C 16 8B 45                                                                                          ..b.X,...b.X,..E
000001C0  97 F5 F5 D9  62 B1 58 2C   16 8B C5 62  B1 58 2C 16                                                                                          ....b.X,...b.X,.
000001D0  8B C5 62 D1  65 7D 7D B6   58 2C 16 8B  C5 62 B1 58                                                                                          ..b.e}}.X,...b.X
000001E0  2C 16 8B C5  62 B1 58 74   59 5F 9F 2D  16 8B C5 62                                                                                          ,...b.XtY_.-...b
000001F0  B1 58 2C 16  8B C5 62 B1   58 2C 16 5D  D6 D7 67 8B                                                                                          .X,...b.X,.]..g.
00000200  C5 62 B1 58  2C 16 8B C5   62 B1 58 2C  16 8B 45 97                                                                                          .b.X,...b.X,..E.
^G Help   ^C Exit (No Save)   ^T goTo Offset   ^X Exit and Sa


```

picoCTF{c0rrupt10n_1847995}
## Notas
En el hexedit se fueron modificando los datos referentes a los chunks de la imagen para que fuera una imagen leíble

## Referencias
http://www.libpng.org/pub/png/spec/1.2/PNG-Chunks.html