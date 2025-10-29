#notas_hacking #cryptography 
## Descripción
What happens if you have a small exponent? There is a twist though, we padded the plaintext so that (M ** e) is just barely larger than N. Let's decrypt this: [ciphertext](https://mercury.picoctf.net/static/a9d46a88f2602fa48edf086a5afbfed8/ciphertext)
## Solución
Como el exponente e es muy pequeño, intentamos invertir la operación sin modulo ya que no tuvo efecto `c = ^ 3` a `m = r3(c)` osea la raíz cubica de c:
```python
import gmpy2

n = 161576568...
e = 3
c = 12200123...

m, es_exacta = gmpy2.iroot(c, e)

if es_exacta:
	print('flag')
else:
	print('no se puede')
______________________________________________________
┌──(kali㉿kali)-[~/pico/crypto]
└─$ /bin/python /home/kali/pico/crypto/mini_rsa/s1.py
no se puede
```
como no logramos una raíz exacta cambiamos, parece ser que `m ^ 3 < n` no es correcta y el modulo si se aplico, entonces pasamos a  intentar un ataque iterativo (ataque de k iterativa), donde `c = m ^ 3 mod n` entonces significa que `m ^ 3` es igual a `c` + (`algun multiplo` * `n`), intentaremos buscar una raíz perfecta iterando `k`:
```python
import gmpy2

n = 1615765...
e = 3
c = 12200...

k = 1
while k < 10000:
	objetivo = c + (k * n)
	m, es_perfecta = gmpy2.iroot(objetivo, e)
	if es_perfecta:
		print('Llegamos')
		flag = bytes.fromhex( hex(m)[2:] ).decode()
		print(flag)
		break
	if k % 100 == 0:
		print('Probando k=', k)
k += 1

if k == 10000:
	print('nada de nada...')
______________________________________________________
┌──(kali㉿kali)-[~/pico/crypto]
└─$ /bin/python /home/kali/pico/crypto/mini_rsa/s2.py
Probando k= 100
Probando k= 200
....
Probando k= 3500
Llegamos
picoCTF{e_sh0u1d_b3_lArg3r_aef7377d}
```
## Notas

## Referencias
