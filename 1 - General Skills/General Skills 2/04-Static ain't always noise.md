#notas_hacking #general_skills
# Reto
## Descripción
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static)? This [BASH script](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh) might help!
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ bash ltdis.sh static 
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
SergioMXZ-picoctf@webshell:~$ cat static.ltdis.strings.txt | grep pico
   1020 picoCTF{d15a5m_t34s3r_f5aeda17}
SergioMXZ-picoctf@webshell:~$ 
```
___
```bash
SergioMXZ-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_f5aeda17}
```
## Notas
bash srcript.sh ejecutable - le pasa el ejecutable al script de bash
## Referencias
