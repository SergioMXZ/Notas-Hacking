#notas_hacking
# Reto
## Descripción
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/26/fixme1.py)
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/26/fixme1.py
...
SergioMXZ-picoctf@webshell:~$ python fixme1.py 
  File "/home/SergioMXZ-picoctf/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
SergioMXZ-picoctf@webshell:~$ nano fixme1.py 
SergioMXZ-picoctf@webshell:~$ python fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
SergioMXZ-picoctf@webshell:~$ 

```
arregle lo que estaba mal alineado 
## Notas
## Referencias