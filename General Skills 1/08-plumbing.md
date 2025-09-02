# Reto
## Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 | grep  pi
coCTF
picoCTF{digital_plumb3r_ea8bfec7}
```
## Notas
| - pasa la un archivo o resultado como entrada de otro gcc ... input.txt | output.txt
permite redirigir la salida de un comando a otro
## Referencias
