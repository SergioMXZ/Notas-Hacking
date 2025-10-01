#notas_hacking #forensic
# Reto
## Descripción
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png).
## Solución
con `exiftool` se pueden mirar la metadata 
```bash
┌──(kali㉿kali)-[~/pico/forence]
└─$ exiftool pico_img.png 
ExifTool Version Number         : 13.25
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2020:10:26 14:38:23-04:00
File Access Date/Time           : 2025:10:01 12:36:25-04:00
File Inode Change Date/Time     : 2025:10:01 12:35:48-04:00
File Permissions                : -rw-rw-r--
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
Artist                          : picoCTF{s0_m3ta_fec06741}
Image Size                      : 600x600
Megapixels                      : 0.360

┌──(kali㉿kali)-[~/pico/forence]
└─$ exiftool -Artist pico_img.png 
Artist                          : picoCTF{s0_m3ta_fec06741}
```
## Notas
`metadata` - datos que describen a otros datos, proporcionando información esencial sobre su contenido, calidad, origen, y otros atributos
## Referencias
