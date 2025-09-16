#notas_hacking
# Reto
## Descripción
I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/138/challenge.zip)
## Solución
```bash
┌──(kali㉿kali)-[~/retos]
└─$ unzip challenge.zip 
...
┌──(kali㉿kali)-[~/retos]
└─$ ls
challenge.zip  drop-in
┌──(kali㉿kali)-[~/retos]
└─$ cd drop-in       
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ ls    
message.txt       
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ cat message.txt 
TOP SECRET
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ ls -la             
total 16
drwxr-xr-x 3 kali kali 4096 Mar 11  2024 .
drwxrwxr-x 3 kali kali 4096 Sep 15 17:07 ..
drwxr-xr-x 8 kali kali 4096 Mar 11  2024 .git
-rw-r--r-- 1 kali kali   11 Mar 11  2024 message.txt
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git init
Reinitialized existing Git repository in /home/kali/retos/drop-in/.git/
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git log                 
commit 42942c9c605b30100f5d859ef6e172027447c0db (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    remove sensitive info

commit b562f0b425907789d11d2fe2793e67592dc6be93
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:23 2024 +0000

    create flag
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git checkout 'b562f0b425907789d11d2fe2793e67592dc6be93'
HEAD is now at b562f0b create flag
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ cat message.txt     
picoCTF{s@n1t1z3_c785c319}
```
Al inspeccionar con un `ls -la` aparece `git`, por lo que hago un `git init` y vemos el registro de los `commits`, cambiamos hacia el antiguo y vemos la bandera
## Notas
## Referencias