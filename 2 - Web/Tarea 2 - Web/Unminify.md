#notas_hacking #web
# Reto
## Descripción
I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster!Browse [here](http://titan.picoctf.net:59153/), and find the flag!
## Solución
todo el html esta en una linea, hacemos un cat en un archivo y aplicamos grep pico
```bash
┌──(kali㉿kali)-[~/pico]
└─$ nano flag.txt       
┌──(kali㉿kali)-[~/pico]
└─$ cat flag.txt | grep picoCTF{
picoCTF{pr3tty_c0d3_b99eb82e}
...
```
no sale así por que esta rodeada de todo de texto, pero se identifica por el resaltado
o desde el navegador puedes elegir con `ctrl` derecho `Wrap Long Lines` o también desde `Accesibility` encontrarla y también con la herramienta `Find in Page...`
## Notas

## Referencias
