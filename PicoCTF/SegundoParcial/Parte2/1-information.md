## Objetivo 
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg)

## Solución
```bash
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2]
└─$ mkdir information
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2]
└─$ cd information 
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/information]
└─$ wget https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg
--2024-03-27 16:20:55--  https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 878136 (858K) [application/octet-stream]
Saving to: ‘cat.jpg’

cat.jpg                        100%[====================================================>] 857.55K   103KB/s    in 13s     

2024-03-27 16:21:11 (66.2 KB/s) - ‘cat.jpg’ saved [878136/878136]

                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/information]
└─$ ls
cat.jpg
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/information]
└─$ strings cat.jpg | grep pico   
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/information]
└─$ exiftool cat.jpg 
ExifTool Version Number         : 12.67
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 12:24:46-06:00
File Access Date/Time           : 2024:03:27 16:24:23-06:00
File Inode Change Date/Time     : 2024:03:27 16:21:11-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
                                                                                                                            
┌──(luispuentes㉿LuisPuentes)-[~/picoCTF/Parcial2/information]
└─$ 
                  
```

picoCTF{the_m3tadata_1s_modified}
## Notas
la bandera estaba encriptada en base 64 en los metadatos de la imagen, específicamente en el dato de la licencia.

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQwYUdWZmJUTjBZV1JoZEdGZk1YTmZiVzlrYVdacFpXUjkNCg&ieol=CRLF&oeol=VT