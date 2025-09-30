#notas_hacking #general_skills
# Reto
## Descripción
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
Start your instance to see connection details.`ssh -p 54195 ctf-player@saturn.picoctf.net`The password is `d8819d45`
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ ssh -p 53117 ctf-player@saturn.picoctf.net
...
Special$ ../../usr/bin/ls
../../usr/bin/ls 
blargh
Special$ ../../usr/bin/cat ./blargh
../../usr/bin/cat ./blargh 
../../usr/bin/cat: ./blargh: Is a directory
Special$ ../../../usr/bin/ls ./blargh
../../../usr/bin/ls ./blargh 
flag.txt
Special$ ../../../usr/bin/cat ./blargh/flag.txt
../../../usr/bin/cat ./blargh/flag.txt 
picoCTF{5p311ch3ck_15_7h3_w0r57_0c61d335}
```
Parecía que ningún comando iba a funcionar pero al agregar `../` como prefijo parecía que no corregía su sintaxis, al no poder ejecutar nada directamente con el nombre de los comandos, te diriges directamente a ejecutarlos desde tu carpeta `../../usr/bin/ls`, esto funciono y mostro algo llamado `blargh` al seguir el mismo procedimiento e intentar hacerle un `cat` (si dejabas `...cat blargh` corregía el nombre, por lo que había que usar el `./blargh` ), resulto ser un directorio, intentamos hacerle un `ls` para ver su contenido y justo tenia la bandera, ya solo quedo ver el contenido de la bandera.
## Notas
`../../usr/bin` - directorio de binarios que tiene la mayoría de los comandos y utilidades que no son esenciales para arrancar el sistema, pero que los usuarios utilizan: `ls`, `cat` etc...
## Referencias
