#notas_hacking #forensic
# Reto
## Descripción
This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.
## Solución
```bash
┌──(kali㉿kali)-[~/pico/forensics]
└─$ open garden.jpg 

┌──(kali㉿kali)-[~/pico/forensics]
└─$ hexeditor garden.jpg         

┌──(kali㉿kali)-[~/pico/forensics]
└─$ strings garden.jpg | grep pico
Here is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"
```
## Notas

## Referencias
