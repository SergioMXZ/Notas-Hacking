#notas_hacking #cryptography 
## Descripción
Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/3/enc_flag).
## Solución

Era aplicar dos beses la `base64` y luego un `ROT` con desplazamiento de 19.
```bash
┌──(kali㉿kali)-[~/pico/crypto]
└─$ cat enc_flag | base64 -d
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ=='

┌──(kali㉿kali)-[~/pico/crypto]
└─$ echo d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ== | base64 -d
wpjvJAM{jhlzhy_k3jy9wa3k_i204hkj6}   
```
`caesar_d3cr9pt3d_b204adc6`
## Notas

## Referencias
