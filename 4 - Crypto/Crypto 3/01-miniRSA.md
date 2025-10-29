#notas_hacking #cryptography 
## Descripción
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/ee7e2388b45f521b285334abb5a63771/ciphertext)? Something seems a bit small.
## Solución
Como el exponente e es muy pequeño, intentamos invertir la operación sin modulo ya que no tuvo efecto `c = ^ 3` a `m = r3(c)` osea la raíz cubica de c:
```python
import gmpy2

n = 293319224...
e = 3
c = 2205316413...

m, es_exacta = gmpy2.iroot(c, e)

if es_exacta:
	flag = bytes.fromhex( hex(m)[2:] ).decode()
	print(f'flag = {flag}')
else:
	print('no se puede')
___________________________________________________
┌──(kali㉿kali)-[~/pico/crypto]
└─$ /bin/python /home/kali/pico/crypto/mini_RSA/s1.py
flag = picoCTF{n33d_a_lArg3r_e_606ce004}
```
## Notas

## Referencias
