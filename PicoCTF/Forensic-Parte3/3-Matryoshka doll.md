## Objetivo 
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/1b70cffdd2f05427fff97d13c496963f/dolls.jpg)

## Solución
```bash
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka$ ls -la
total 640
drwxrwxrwx 1 luisillo luisillo   4096 Mar 22 11:04 .
drwxrwxrwx 1 luisillo luisillo   4096 Mar 22 11:04 ..
-rwxrwxrwx 1 luisillo luisillo 651634 Mar 15  2021 dolls.jpg
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383938, name: base_images/2_c.jpg
651612        0x9F15C         End of Zip archive, footer length: 22

luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka$ binwalk -e dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8

WARNING: Extractor.execute failed to run external extractor 'unzip -o '%e'': [Errno 2] No such file or directory: 'unzip', 'unzip -o '%e'' might not be installed correctly
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383938, name: base_images/2_c.jpg
651612        0x9F15C         End of Zip archive, footer length: 22

luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka$ ls
_dolls.jpg.extracted  dolls.jpg
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka$ cd _dolls.jpg.extracted/
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted$ ls
4286C.zip  base_images
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted$ cd base_images/
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images$ ls
2_c.jpg
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images$ binwalk 2_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196043, uncompressed size: 201445, name: base_images/3_c.jpg
383805        0x5DB3D         End of Zip archive, footer length: 22
383916        0x5DBAC         End of Zip archive, footer length: 22

luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images$ binwalk -e 2_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8

WARNING: Extractor.execute failed to run external extractor 'unzip -o '%e'': [Errno 2] No such file or directory: 'unzip', 'unzip -o '%e'' might not be installed correctly
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196043, uncompressed size: 201445, name: base_images/3_c.jpg
383805        0x5DB3D         End of Zip archive, footer length: 22
383916        0x5DBAC         End of Zip archive, footer length: 22

luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images$ ls
2_c.jpg  _2_c.jpg.extracted
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images$ cd _2_c.jpg.extracted/
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted$ ls
2DD3B.zip  base_images
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted$ cd base_images/
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ ls
3_c.jpg
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ binwalk -e 3_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8

WARNING: Extractor.execute failed to run external extractor 'unzip -o '%e'': [Errno 2] No such file or directory: 'unzip', 'unzip -o '%e'' might not be installed correctly
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77651, uncompressed size: 79807, name: base_images/4_c.jpg
201423        0x312CF         End of Zip archive, footer length: 22

luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ ls
3_c.jpg  _3_c.jpg.extracted
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ cd _3_c.jpg.extracted/
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted$ ls
1E2D6.zip  base_images
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted$ cd base_images/
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ ls
4_c.jpg
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ binwalk -e 4_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8

WARNING: Extractor.execute failed to run external extractor 'unzip -o '%e'': [Errno 2] No such file or directory: 'unzip', 'unzip -o '%e'' might not be installed correctly
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 63, uncompressed size: 81, name: flag.txt
79785         0x137A9         End of Zip archive, footer length: 22

luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ ls
4_c.jpg  _4_c.jpg.extracted
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ cd _
-bash: cd: _: No such file or directory
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ cd _4_c.jpg.extracted/
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted$ ls
136DA.zip  flag.txt
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted$ cat flag.txt
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}
luisillo@DESKTOP-8T8TJ1H:/mnt/c/milinux/KL_FS/matroshka/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted$
```

## Notas
al notar que cada vez que se descomprime el archivo, se puede volver a descomprimir, se comienza a decomprimir todo hasta topar con el final

## Referencias
Manual de usuario del comando binwalk
https://es.wikipedia.org/wiki/Matroska
