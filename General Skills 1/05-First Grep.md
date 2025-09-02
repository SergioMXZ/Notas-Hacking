# Reto
## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.
## Solución
picoCTF{grep_is_good_to_find_things_dba08a45}
Descargar archivo en la consola con wget, usar wc para contar y grep para encontrar el patrón de la key
```bash
SergioMXZ-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
--2025-09-01 17:05:57--  https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: 'file'

file                100%[===================>]  14.21K  --.-KB/s    in 0s      

2025-09-01 17:05:57 (335 MB/s) - 'file' saved [14551/14551]

SergioMXZ-picoctf@webshell:~$ wc file
    6   309 14551 file
SergioMXZ-picoctf@webshell:~$ grep 'picoCTF' file
picoCTF{grep_is_good_to_find_things_dba08a45}
```
## Notas
wget - descarga desde la terminal
wc - cuenta lineas, caracteres y bytes
grep - encuentra un patron en un archivo
file - me permite saber el tipo archivo
## Referencias