#notas_hacking #forensic
## Descripción

## Solución
Hacemos el mismo procedimiento que con el reto `WebNet0` de agregar la `key`, pero en este caso vemos que se intercambiaron una imagen.
Para ver y guardar la imagen vamos a `File > Export Objects > HTTP...` donde esta la imagen y desde aquí en `Save` la guardamos, en donde con strings extraemos la bandera de su contenido.
```bash
┌──(kali㉿kali)-[~/pico/Forensic3/Webnet1]
└─$ ls
capture.pcap  picopico.key  vulture.jpg
┌──(kali㉿kali)-[~/pico/Forensic3/Webnet1]
└─$ strings -n 10 vulture.jpg                                    
picoCTF{honey.roasted.peanuts}
ICC_PROFILE
mntrRGB XYZ 
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
%'c^;XRs(A
-%0c;I?Q^Gq~
_jDrp3\576
;PFM/cY5wp
z8i9J+}Gf|
```

o igual desde el buscador de `wireshark`, o también directamente con `ssldump`.
```bash
┌──(kali㉿kali)-[~/pico/Forensic3/Webnet1]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep -A2 picoCTF
    61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73    ag: picoCTF{this
    2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61    .is.not.your.fla
    67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74    g.anymore}..Cont
--
    67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e    g: picoCTF{this.
    69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67    is.not.your.flag
    2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65    .anymore}..Conte
--
    Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
    Keep-Alive: timeout=5, max=99
    Connection: Keep-Alive
--
    00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b    ........picoCTF{
    68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65    honey.roasted.pe
    61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f    anuts}......ICC_
Cleaned 4 remaining connection(s) from connection pool
```
## Notas

## Referencias
