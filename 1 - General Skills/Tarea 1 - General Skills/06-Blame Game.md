#notas_hacking #general_skills
# Reto
## Descripción
Someone's commits seems to be preventing the program from working. Who is it? You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/72/challenge.zip)
## Solución
```bash
┌──(kali㉿kali)-[~/retos]
└─$ wget https://artifacts.picoctf.net/c_titan/72/challenge.zip 
...     
┌──(kali㉿kali)-[~/retos]
└─$ unzip challenge.zip
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ cat message.py                                         
print("Hello, World!"
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git log --follow message.py                            
commit 9ae3e1bc67ad0143c611c5f65399b79850d20983
Author: picoCTF{@sk_th3_1nt3rn_b64c4705} <ops@picoctf.com>
Date:   Sat Mar 9 21:09:01 2024 +0000

    optimize file size of prod code

commit f3cec26cf7f80f91b5c3d1972f14dd4e9f97ec83
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:01 2024 +0000

    create top secret project
```
La llave es el nombre del autor del `commit` *picoCTF{@sk_th3_1nt3rn_b64c4705}*
## Notas
`git log --follow [file]` - muestra los `commits` que cambiaron el archivo, incluso los cambios de nombre
## Referencias
https://education.github.com/git-cheat-sheet-education.pdf