#notas_hacking #forensic
## Descripción
How about some hide and seek? Download this file [here](https://artifacts.picoctf.net/c_titan/130/unknown.zip).
## Solución
dentro de los meta datos de la imagen estaba la bandera en base 64
```bash
┌──(kali㉿kali)-[~/pico/Tarea3_forensic/canyousee]
└─$ exiftool ukn_reality.jpg
ExifTool Version Number         : 13.25
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:03:11 20:05:55-04:00
File Access Date/Time           : 2025:10:25 21:27:06-04:00
File Inode Change Date/Time     : 2025:10:25 21:26:44-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fNmE5ZjVhYzR9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4

└─$ exiftool -AttributionURL  ukn_reality.jpg 
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fNmE5ZjVhYzR9Cg==
┌──(kali㉿kali)-[~/pico/Tarea3_forensic/canyousee]
└─$ echo cGljb0NURntNRTc0RDQ3QV9ISUREM05fNmE5ZjVhYzR9Cg | base64 -d
picoCTF{ME74D47A_HIDD3N_6a9f5ac4}
```
## Notas

## Referencias
