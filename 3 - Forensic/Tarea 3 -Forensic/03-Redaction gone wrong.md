#notas_hacking #forensic
## Descripción
Now you DON’T see me. This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
## Solución
Simplemente seleccionando texto en el `pdf` pude ver la flag, pero con la herramienta `pdftotext` puedes pasar el `pdf` a texto:
```bash
┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ pdftotext Financial_Report_for_ABC_Labs.pdf

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ ls                                              
cat.jpg  Financial_Report_for_ABC_Labs.pdf  Financial_Report_for_ABC_Labs.txt  pico.flag.png

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ cat Financial_Report_for_ABC_Labs.txt | grep pico
picoCTF{C4n_Y0u_S33_m3_fully}
```
## Notas

## Referencias
