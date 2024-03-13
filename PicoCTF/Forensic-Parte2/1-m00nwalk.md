## Objetivo 
Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

## Solución
```bash
──(luispuentes㉿kali)-[~/picoctf/forensic/moonwalk]
└─$ ls
message.wav

┌──(luispuentes㉿kali)-[~/picoctf/forensic/moonwalk]
└─$ file message.wav 
message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz

┌──(luispuentes㉿kali)-[~/picoctf/forensic/moonwalk]
└─$ strings -n 10 message.wav | grep pico

┌──(luispuentes㉿kali)-[~/picoctf/forensic/moonwalk]
└─$ hexeditor message.wav 

┌──(luispuentes㉿kali)-[~/picoctf/forensic/moonwalk]
└─$ exiftool message.wav 
ExifTool Version Number         : 12.67
File Name                       : message.wav
Directory                       : .
File Size                       : 11 MB
File Modification Date/Time     : 2020:10:26 12:30:20-06:00
File Access Date/Time           : 2024:03:13 12:11:17-06:00
File Inode Change Date/Time     : 2024:03:13 12:09:32-06:00
File Permissions                : -rw-r--r--
File Type                       : WAV
File Type Extension             : wav
MIME Type                       : audio/x-wav
Encoding                        : Microsoft PCM
Num Channels                    : 1
Sample Rate                     : 48000
Avg Bytes Per Sec               : 96000
Bits Per Sample                 : 16
Duration                        : 0:01:55

┌──(luispuentes㉿kali)-[~/picoctf/forensic/moonwalk]
└─$ sstv -d message.wav -o img.jpg
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!

┌──(luispuentes㉿kali)-[~/picoctf/forensic/moonwalk]
└─$ ls
img.jpg  message.wav

┌──(luispuentes㉿kali)-[~/picoctf/forensic/moonwalk]
└─$ open img.jpg 


```
picoCTF{beep_boop_im_in_space}

## Notas
con file archivo podemos ver que tipo de archivo es el analizado
sstv es un decodificador
## Referencias
https://github.com/colaclanth/sstv

