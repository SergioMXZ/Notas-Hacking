#notas_hacking
# Reto
## Descripción
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/23/convertme.py)
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/23/convertme.py
...
SergioMXZ-picoctf@webshell:~$ nano convertme.py
...
SergioMXZ-picoctf@webshell:~$ python convertme.py
If 16 is in decimal base, what is it in binary base?
0b10000
Answer: 10000
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}
SergioMXZ-picoctf@webshell:~$ 
```
cambie una línea del código con nano, este cambio imprime el numero en booleano para saber la respuesta
## Notas
## Referencias
