#notas_hacking #forensic
## Descripción
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.
## Solución
En base a las pistas descargamos la herramienta 
```bash
┌──(kali㉿kali)-[/opt]
└─$ sudo git clone https://github.com/colaclanth/sstv.git
```
la usamos para decodificar el audio a `png`
```
┌──(kali㉿kali)-[~/pico/forensics_2/m00nwalk]
└─$ sstv -d message.wav -o result.png                            
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
```
rotamos la imagen y contiene:
`picoCTF{beep_boop_im_in_space}`
## Notas

## Referencias
