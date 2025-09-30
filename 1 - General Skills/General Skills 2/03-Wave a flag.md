#notas_hacking #general_skills
# Reto
## Descripción
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm) has extraordinarily helpful information...
## Solución
Primero descargamos el archivo, con el comando file nos damos cuenta que es un ejecutable, cambiamos los permisos para darle de ejecución y al ejecutarlo nos da la instrucción de que le pasemos el -h de ayuda
```bash
SergioMXZ-picoctf@webshell:~$ wpeg https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
-bash: wpeg: command not found
SergioMXZ-picoctf@webshell:~$ wpet https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
-bash: wpet: command not found
SergioMXZ-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
2025-09-03 16:51:43 (330 MB/s) - 'warm' saved [10936/10936]

SergioMXZ-picoctf@webshell:~$ file warm 
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=3aa19b2a9cc4e093d64025eab8f510679b523455, with debug_info, not stripped
SergioMXZ-picoctf@webshell:~$ chmod +x warm 
SergioMXZ-picoctf@webshell:~$ ./warm 
Hello user! Pass me a -h to learn what I can do!
SergioMXZ-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_30e77291}
```
## Notas
file - te muestra la información del archivo
./ejecutable -h - esto invoca la ayuda de un ejecutable
ctrl + - letra mas grande
ctrl - - letra mas pequeño
ctrl l - borra la pantalla
ctrl a - navega al inicio
ctrl e - navega al final
## Referencias
