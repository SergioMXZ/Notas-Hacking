#notas_hacking #forensic
## Descripción

## Solución
dentro había un archivo zip y una carpeta secret que tenia la flag
```bash
┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ zsteg -a flag.png
[?] 3198 bytes of extra data after image end (IEND), offset = 0x9b3b
extradata:0         .. file: Zip archive data, made by v3.0 UNIX, extract using at least v1.0, last modified Mar 16 2023 02:01:50, uncompressed size 0, method=store
...
┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ binwalk flag.png                            

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2876, uncompressed size: 3029, name: secret/flag.png
42915         0xA7A3          End of Zip archive, footer length: 22

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ unzip flag.png     
Archive:  flag.png
warning [flag.png]:  39739 extra bytes at beginning or within zipfile
  (attempting to process anyway)
   creating: secret/
  inflating: secret/flag.png         

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ ls
cat.jpg                            Financial_Report_for_ABC_Labs.txt  flag.png.1     scan_surprise
Financial_Report_for_ABC_Labs.pdf  flag.png                           pico.flag.png  secret

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ cd secret       

┌──(kali㉿kali)-[~/pico/Tarea3_forensic/secret]
└─$ ls
flag.png

┌──(kali㉿kali)-[~/pico/Tarea3_forensic/secret]
└─$ open flag.png 
```

`picoCTF{Hiddinng_An_imag3_within_@n_ima9e_d55982e8}`
## Notas

## Referencias
