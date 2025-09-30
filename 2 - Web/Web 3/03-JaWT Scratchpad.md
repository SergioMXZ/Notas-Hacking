#notas_hacking #web
# Reto
## Descripción
`Internal server errors can be intentionally returned by this challenge. If you experience one, try clearing your cookies.`

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210
`hint` : Have you heard of JWT?
## Solución
usamos el diccionario `rockyou.txt` y con la herramienta `jhon` crackea la llave con la que fue encriptada
```bash
┌──(kali㉿kali)-[~]
└─$ john hash -w-/usr/share/wordlists/rockyou.txt 
Unknown option: "-w-/usr/share/wordlists/rockyou.txt"   
┌──(kali㉿kali)-[~]
└─$ john hash -w=/usr/share/wordlists/rockyou.txt
...
ilovepico        (?)     
...
```
con este código cambiamos la `cookie` `jwt` a `admin` sin afectar sus otras partes 
`picoCTF{jawt_was_just_what_you_thought_44c752f5}`
## Notas
## Referencias
https://www.jwt.io/introduction
https://www.jwt.io/