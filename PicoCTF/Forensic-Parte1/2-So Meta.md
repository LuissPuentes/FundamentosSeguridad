## Objetivo 
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).

## Solución
```bash

┌──(luispuentes㉿kali)-[~/picoctf/forensic/SoMeta]
└─$ ls
pico_img.png

┌──(luispuentes㉿kali)-[~/picoctf/forensic/SoMeta]
└─$ exiftool pico_img.png
ExifTool Version Number         : 12.67
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2020:10:26 12:38:23-06:00
File Access Date/Time           : 2024:03:13 13:56:22-06:00
File Inode Change Date/Time     : 2024:03:13 13:56:22-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_d8944929}
Image Size                      : 600x600
Megapixels                      : 0.360

┌──(luispuentes㉿kali)-[~/picoctf/forensic/SoMeta]
└─$ exiftool pico_img.png -Artist
Artist                          : picoCTF{s0_m3ta_d8944929}

┌──(luispuentes㉿kali)-[~/picoctf/forensic/SoMeta]
└─$ 
```


## Notas
exiftool nos muestra información de la imagen donde pueden venir datos interesantes

## Referencias
Manual de usuario comando exiftool