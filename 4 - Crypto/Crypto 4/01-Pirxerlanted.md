#notas_hacking #cryptography 
## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/1594c3f1980e3fb93df09a6d02f53904/scrambled2.png)****
## Solución 
Hay dos maneras, la primera es con un programa de `python` en donde manualmente fusionamos ambas imágenes:
``` python
from PIL import Image
import numpy as np

imagen1 = np.asarray( Image.opne('scrambled1.png') )
imagen2 = np.asarray( Image.opne('scrambled2.png') )

todo = imagen1 + imagen2

nuueva = Image.fromarray(todo)

nueva.save('flag2.png', 'PNG')
```
 ejecutamos, y aparece la dentro de esta imagen la bandera:
```python
┌──(kali㉿kali)-[~/pico/crypto/cp4]
└─$ nano exp.py  

┌──(kali㉿kali)-[~/pico/crypto/cp4]
└─$ python exp.py

┌──(kali㉿kali)-[~/pico/crypto/cp4]
└─$ open flag.png
```
también desde la terminal se puede componer la bandera:
```python
┌──(kali㉿kali)-[~/pico/crypto/cp4]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite flag.png 

┌──(kali㉿kali)-[~/pico/crypto/cp4]
└─$ open flag.png
```
## Notas

## Referencias
