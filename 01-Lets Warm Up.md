# Reto
## Descripción
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?
## Solución
- Usar una pagina web de conversión hex to ascii
- Usar la herramienta web  CyberChef
- Usar la terminal incorporada u otra con Python y sus funciones de conversión 
```bash
SergioMXZ-picoctf@webshell:~$ python
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> int(0x70)
112
>>> chr(112)
'p'
```

- Manera en la que se envía la Key en PicoCTF
```
picoCTF{p}
```
## Notas
## Referencias
- [CyberChef](https://gchq.github.io/CyberChef/)