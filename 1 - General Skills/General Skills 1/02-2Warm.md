#notas_hacking #general_skills
# Reto
## Descripción
Can you convert the number 42 (base 10) to binary (base 2)?
## Solución
42 > BINARIO
###### Restando potencias
Tomas las potencias de 2 y vas restando desde la potencia menor
o igual inmediatamente mayor al numero hasta terminar con un 0,
cuándo un numero puede restarlo se asigna un 1 y cuando no en 0

| 126 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 0   | 1   | 0   | 1   | 0   | 1   | 0   |
###### Con la función "bin()" de python
``` bash
SergioMXZ-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)
'0b101010'
```
## Notas
## Referencias
