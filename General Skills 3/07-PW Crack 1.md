#notas_hacking
# Reto
## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.py
2025-09-10 17:01:54 (228 MB/s) - 'level1.py' saved [876/876]
SergioMXZ-picoctf@webshell:~$ wget
...
SergioMXZ-picoctf@webshell:~$ python level1.py 
Please enter correct password for flag: 
SergioMXZ-picoctf@webshell:~$ nano level1.py
...
SergioMXZ-picoctf@webshell:~$ python level1.py 
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
SergioMXZ-picoctf@webshell:~$
```
leí la contraseña desde el código
## Notas
## Referencias
