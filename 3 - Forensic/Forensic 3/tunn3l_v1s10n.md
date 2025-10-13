#notas_hacking #forensic
## Descripción
We found this [file](https://mercury.picoctf.net/static/da18eed3d15fd04f7b076bdcecf15b27/tunn3l_v1s10n). Recover the flag.
## Solución
Parece que no sabe que es pues solo aparece como `data`
```bash
┌──(kali㉿kali)-[~/pico/Forensic3/tunn3l_v1s10n]
└─$ file tunn3l_v1s10n 
tunn3l_v1s10n: data
```
Al intentar abrirla nos aparece un error que nos dice `BMP image has unsupported header size`
corregimos el tamaño osea el `Header Size` el cual debería de ser 40 bytes por estándar, entonces agregamos al Offset `0x0E` un 28 osea hexadecimal 40, también debo corregir donde empiezan los datos, que es 28 y quitar el D que sobra a 0.
Al abrir la imagen aparece un mensaje de que no es la bandera, cambiamos su tamaño para que sea igual mas uniforme en el `0x16 y 0x17` que controlan el alto y los cambiamos al mismo ancho que los  `0x12 y 0x13`,  y encontramos la bandera.
```bash
┌──(kali㉿kali)-[~/pico/Forensic3/tunn3l_v1s10n]
└─$ hexeditor tunn3l_v1s10n
```
y en la imagen aparece la bandera:
`picoCTF{qu1t3_a_v13w_2020}`
## Notas

## Referencias
