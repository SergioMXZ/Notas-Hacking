#notas_hacking #forensic
## Descripción
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/97/flag2of2-final.pdf).
## Solución
Extraje el texto del `pdf`, luego me di cuenta que aparecía como archivo `png`, por lo que lo convertí y al mirarlo tenia la parte faltan te de la bandera
```bash
┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ pdftotext flag2of2-final.pdf

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ cat flag2of2-final.txt
1n_pn9_&_pdf_724b1287}

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ file flag2of2-final.pdf                 
flag2of2-final.pdf: PNG image data, 50 x 50, 8-bit/color RGBA, non-interlaced

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ mv flag2of2-final.pdf flag2of2-final.png

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ mv flag2of2-final.pdf flag2of2-final.png

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ open flag2of2-final.png
```
`picoCTF{f1u3n7_` como `png`
`1n_pn9_&_pdf_724b1287}` como `pdf`

`picoCTF{f1u3n7_1n_pn9_&_pdf_724b1287}`
## Notas

## Referencias
