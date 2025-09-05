# Reto
## Descripción
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.zip)
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b
7298/Addadshashanammu.zip
...
SergioMXZ-picoctf@webshell:~$ unzip Addadshashanammu.zip 
...
SergioMXZ-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  README.txt
Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelk
ashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}
```
## Notas
tab - auto completado
cd enter - carpeta del usuario
cd - enter - te devuelve al directorio anterior
## Referencias
