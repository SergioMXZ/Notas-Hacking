#notas_hacking #forensic
# Reto
## Descripción
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?
## Solución

```bash
┌──(kali㉿kali)-[~/pico/forensics]
└─$ open buildings.png            
┌──(kali㉿kali)-[~/pico/forensics]
└─$ strings buildings.png | grep pico

┌──(kali㉿kali)-[~/pico/forensics]
└─$ sudo gem install zsteg                             
...                 
┌──(kali㉿kali)-[~/pico/forensics]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
```

## Notas
`zsteg` - es una herramienta de software, escrita en Ruby y distribuida como una gema, que se utiliza para detectar esteganografía (datos ocultos) en archivos de imagen, principalmente PNG y BMP, aunque también puede procesar datos comprimidos con zlib
## Referencias
[que es la estenografía?][https://latam.kaspersky.com/resource-center/definitions/what-is-steganography]