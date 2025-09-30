#notas_hacking #general_skills
# Reto
## Descripción
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/5/fixme2.py)
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/5/fixme2.py
...
SergioMXZ-picoctf@webshell:~$ python fixme2.py 
  File "/home/SergioMXZ-picoctf/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
SergioMXZ-picoctf@webshell:~$ nano fixme2.py 
SergioMXZ-picoctf@webshell:~$ python fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
SergioMXZ-picoctf@webshell:~$ 
```
arregle el error en donde estaba asignando en lugar de comparar
## Notas
## Referencias
