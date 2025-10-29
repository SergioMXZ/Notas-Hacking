#notas_hacking #cryptography 
## Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values
## Solución
Factor-izamos `n` para poder conseguir `p` y `q` ,  completar los pasos hasta la bandera, esto es posible por la n es muy pequeña
```python
c = 62324783949134119159408816513334912534343517300880137691662780895409992760262021
n = 1280678415822214057864524798453297819181910621573945477544758171055968245116423923
e = 65537

p = 1899107986527483535344517113948531328331
q = 674357869540600933870145899564746495319033

tn = (p - 1) * (q - 1)

d = pow(e, -1, tn)

m = pow(c, d, n)

flag = bytes.fromhex( hex(m)[2:] ).decode()
print(flag)
___________________________________________________
┌──(kali㉿kali)-[~/pico/crypto]
└─$ /bin/python /home/kali/pico/crypto/mind_your_ps_and_qs/s3.py
picoCTF{sma11_N_n0_g0od_05012767}
```
## Notas
https://factordb.com/
## Referencias
