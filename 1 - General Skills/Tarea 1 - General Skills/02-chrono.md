#notas_hacking #general_skills
# Reto
## Descripción
How to automate tasks to run at intervals on linux servers?
Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 52639
Username: picoplayer 
Password: bLgSMmbY6X
```
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ ssh picoplayer@saturn.picoctf.net -p 53479
...
picoplayer@challenge:~$ ls 
picoplayer@challenge:~$ chrono
-bash: chrono: command not found
picoplayer@challenge:~$ ls /
...
picoplayer@challenge:~$ cat /etc/cron
cat: /etc/cron: No such file or directory
picoplayer@challenge:~$ cat /etc/crontab 
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_1b4d8744}
picoplayer@challenge:~$ 
```
parecía que tenia que ver con la palabra Chrono pero investigando tal vez se refería a `cron` en Linux, y en su descripcion mencionaba que las tareas que ejecutaba estaban en los archivos `contab`, por lo que al buscarlo y hacerle un cat me dio la llave
## Notas
`cron` - Es un servicio (demonio) que ejecuta tareas programadas de forma automática en intervalos regulares, como archivos de configuración y scripts. 
`crontab` - Es el archivo de configuración que contiene las tareas programadas y sus horarios. Cada usuario tiene el suyo propio.
## Referencias
