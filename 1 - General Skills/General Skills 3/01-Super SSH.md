#notas_hacking #general_skills
# Reto
## Descripción
Using a Secure Shell (SSH) is going to be pretty important.

Additional details will be available after launching your challenge instance.
Using a Secure Shell (SSH) is going to be pretty important.Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `53210` to get the flag?You'll also need the password `6dd28e9b`. If asked, accept the fingerprint with `yes`.
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ ssh ctf-player@titan.picoctf.net -p 53210
The authenticity of host '[titan.picoctf.net]:53210 ([3.139.174.234]:53210)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:53210' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_5d09a462}
Connection to titan.picoctf.net closed.
```
## Notas
## Referencias
