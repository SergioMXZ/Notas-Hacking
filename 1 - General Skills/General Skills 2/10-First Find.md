#notas_hacking #general_skills
# Reto
## Descripción
Unzip this archive and find the file named 'uber-secret.txt'
- [Download zip file](https://artifacts.picoctf.net/c/500/files.zip)
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/500/files.zip
...
SergioMXZ-picoctf@webshell:~$ unzip files.zip 
...
SergioMXZ-picoctf@webshell:~$ find files -name uber-secret.txt
files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
SergioMXZ-picoctf@webshell:~$ cd files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
SergioMXZ-picoctf@webshell:~/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ cat uber-secret.txt 
picoCTF{f1nd_15_f457_ab443fd1}
```
## Notas
find - se usa para buscar archivos
find . -name nombre.txt - esto busca dentro del directorio actual con el nombre exacto
-iname - agregando esa i ignora las mayúsculas y minúsculas
## Referencias
