#notas_hacking
# Reto
## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.py
2025-09-10 17:13:50 (385 MB/s) - 'level3.py' saved [1337/1337]
SergioMXZ-picoctf@webshell:~$ wget 
2025-09-10 17:13:58 (17.0 MB/s) - 'level3.flag.txt.enc' saved [31/31]
SergioMXZ-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/16/level3.hash.bin
2025-09-10 17:14:06 (310 KB/s) - 'level3.hash.bin' saved [16/16]
SergioMXZ-picoctf@webshell:~$ python level3.py 
Please enter correct password for flag: d
That password is incorrect
SergioMXZ-picoctf@webshell:~$ nano level3.py
...
SergioMXZ-picoctf@webshell:~$ python level3.py 
~fo=M[J)c;9:Qi`c`h=<iP>0>8>37?q
{>52H&fcc5T1:le0g3d?;`d<2g+
.o7iR}32an`870aeh9Yfdn1fgg6)
|=g=OB)a`1:S2hcb35<k
                    60<c635dy
-<d=A)0a2:3kc326<:
50mb53dez
|:`<OE(ag6;S5obb42=k
                    11<d125c~
picoCTF{m45h_fl1ng1ng_2b072a90}
SergioMXZ-picoctf@webshell:~$ 
```
modifique para pintar todos los hash con las posibles contraseñas
## Notas
## Referencias
