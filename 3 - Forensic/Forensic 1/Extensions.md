#notas_hacking #forensic
# Reto
## Descripción
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
## Solución
cambiar la extension, la imagen contiene la llave
```bash
┌──(kali㉿kali)-[~/pico/forensics]
└─$ file flag.txt                                                                         
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

┌──(kali㉿kali)-[~/pico/forensics]
└─$ mv flag.txt flag.png                                                

┌──(kali㉿kali)-[~/pico/forensics]
└─$ open flag.png
```

`picoCTF{now_you_know_about_extensions}`
## Notas

## Referencias
