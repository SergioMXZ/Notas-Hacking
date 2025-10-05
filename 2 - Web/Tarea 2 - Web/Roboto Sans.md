#notas_hacking #web
# Reto
## Descripción
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:65513/) out.
## Solución
http://saturn.picoctf.net:61102/robots.txt
```txt
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```
posible base64
```base64
ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
```
to base 64 en CyberChef
```txt
flag1.txtjs/myfif§2ö×fÆRçG@/²Ë!®	h²÷Z²W£ <-- todo junto
flag1.txtjs/myfi                               <-- primer linea
js/myfile.txt                                  <-- segunda linea
```
`flag1.txt` = 404 Not Found
`js/myfile.txt` = `picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}`
## Notas

## Referencias
