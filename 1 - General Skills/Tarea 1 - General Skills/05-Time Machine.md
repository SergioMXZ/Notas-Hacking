#notas_hacking #general_skills
# Reto
## Descripción
What was I last working on? I remember writing a note to help me remember... You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/162/challenge.zip)
## Solución
```bash
┌──(kali㉿kali)-[~/retos]
└─$ wget https://artifacts.picoctf.net/c_titan/162/challenge.zip                 
┌──(kali㉿kali)-[~/retos]
└─$ ls
challenge.zip                    
┌──(kali㉿kali)-[~/retos]
└─$ unzip challenge.zip 
...
┌──(kali㉿kali)-[~/retos]
└─$ ls
challenge.zip  drop-in
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ ls        
message.txt            
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ cat message.txt
This is what I was working on, but Id need to look at my commit history to know why... 
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git log                                                
commit 712314f105348e295f8cadd7d7dc4e9fa871e9a2 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:26 2024 +0000

    picoCTF{t1m3m@ch1n3_e8c98b3a}
```
## Notas
## Referencias
