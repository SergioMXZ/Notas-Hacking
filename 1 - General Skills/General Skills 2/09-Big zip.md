#notas_hacking #general_skills
# Reto
## Descripción
Unzip this archive and find the flag.
- [Download zip file](https://artifacts.picoctf.net/c/504/big-zip-files.zip)
## Solución
``` bash
SergioMXZ-picoctf@webshell:~$ ls
README.txt  big-zip-files  big-zip-files.zip
SergioMXZ-picoctf@webshell:~$ cd big-zip-files/
SergioMXZ-picoctf@webshell:~/big-zip-files$ ls
... muchos archivos
SergioMXZ-picoctf@webshell:~$ ls           
README.txt  big-zip-files  big-zip-files.zip
SergioMXZ-picoctf@webshell:~$ grep -r pico big-zip-files
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
```
## Notas
grep -r patrón directorio - -r significa recursivo, entonces grep busca el patrón dentro del directorio y subdirectorios y dentro de estos en los archivos
... -r patrón . - busca en los archivos del directorio actual y sus sub...
grep patrón directorio/* - busca en todos los archivos del directorio
## Referencias
