#notas_hacking #forensic
## Descripción
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/c0da20f29337e87ffb58ea987d8c596e/Forensics%20is%20fun.pptm)
## Solución
al descomprimir nos damos cuenta que el ultimo archivo se llama hidden, le hacemos un cat y parecen ser caracteres con espacios
```
┌──(kali㉿kali)-[~/pico/Forensic3/MacroHard]
└─$ file 'Forensics is fun.pptm' 
Forensics is fun.pptm: Microsoft PowerPoint 2007+
                                                                                                                 
┌──(kali㉿kali)-[~/pico/Forensic3/MacroHard]
└─$ unzip 'Forensics is fun.pptm' 
...
  inflating: ppt/slideMasters/hidden  
┌──(kali㉿kali)-[~/pico/Forensic3/MacroHard]
└─$ cat ppt/slideMasters/hidden 
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q     
```
le quitamos los espacios y parece estar en `base64`
```
┌──(kali㉿kali)-[~/pico/Forensic3/MacroHard]
└─$ cat  ppt/slideMasters/hidden | tr -d ' '
ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQ
┌──(kali㉿kali)-[~/pico/Forensic3/MacroHard]
└─$ cat  ppt/slideMasters/hidden | tr -d ' ' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}      
```
## Notas
un archivo `pptm` no deja de ser un un archivo comprimido
## Referencias
