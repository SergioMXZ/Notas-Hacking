#notas_hacking #general_skills
# Reto
## Descripción
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 22902`, but it doesn't speak English...
## Solución
Se conecta al puerto y redirige la salida a un archivo, dentro de Python leemos este archivo,
recorremos las líneas de este y convertimos a entero y luego a char, mostrando este ultimo,
lo que nos da como resultado la llave
```bash
SergioMXZ-picoctf@webshell:~$ nc mercury.picoctf.net 22902 > file
^C
SergioMXZ-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> f = open('file', 'r')
>>> for line in f:
...     line = line.strip()
...     num = int(line)
...     print(chr(num), end='')
... 
picoCTF{g00d_k1tty!_n1c3_k1tty!_d3dfd6df}
```
## Notas
'>' - redirige la salida de un comando hacia otro
## Referencias
