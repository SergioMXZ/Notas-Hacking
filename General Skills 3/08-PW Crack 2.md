#notas_hacking
# Reto
## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ python level2.py 
Please enter correct password for flag: c
That password is incorrect
SergioMXZ-picoctf@webshell:~$ nano level2.py
SergioMXZ-picoctf@webshell:~$ python level2.py 
4ec9
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
SergioMXZ-picoctf@webshell:~$ 
```
modifique el archivo para que pinte la contraseña antes de pedirla
## Notas
## Referencias
