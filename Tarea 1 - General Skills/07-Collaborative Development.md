#notas_hacking
# Reto
## Descripción
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together? You can download the challenge files here:
## Solución
```bash
--descarga--y--descompresion--
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ ls
flag.py
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ cat flag.py 
print("Printing the flag...")
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git branch          
  feature/part-1
  feature/part-2
  feature/part-3
* main
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git merge feature/part-1
Updating eb19d0e..0cd57e0
Fast-forward
 flag.py | 1 +
 1 file changed, 1 insertion(+)
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ cat flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')                                  
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git merge feature/part-2
Auto-merging flag.py
CONFLICT (content): Merge conflict in flag.py
Automatic merge failed; fix conflicts and then commit the result.
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ nano flag.py
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git add flag.py         
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git commit -m unido 
[main 216782a] unido
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git merge feature/part-3
Auto-merging flag.py
CONFLICT (content): Merge conflict in flag.py
Automatic merge failed; fix conflicts and then commit the result.
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ nano flag.py
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git add flag.py         
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ git commit -m unido     
[main a8a21a4] unido
┌──(kali㉿kali)-[~/retos/drop-in]
└─$ python flag.py      
Printing the flag...
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}
```
## Notas
## Referencias
