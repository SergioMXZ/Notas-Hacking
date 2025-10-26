#notas_hacking #forensic
## Descripción
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/14/challenge.zip)

The same files are accessible via SSH here: `ssh -p 60817 ctf-player@atlas.picoctf.net` Using the password `84b12bae`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
## Solución
Usamos la herramienta que recomiendan las pistas para escanear el código qr a texto
```bash
┌──(kali㉿kali)-[~/…/scan_surprise/home/ctf-player/drop-in]
└─$ sudo apt-get install zbar-tools

┌──(kali㉿kali)-[~/…/scan_surprise/home/ctf-player/drop-in]
└─$ zbarimg flag.png 
QR-Code:picoCTF{p33k_@_b00_0194a007}
scanned 1 barcode symbols from 1 images in 0.02 seconds
```

`picoCTF{p33k_@_b00_0194a007}`
## Notas

## Referencias
