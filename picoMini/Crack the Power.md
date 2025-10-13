#notas_hacking #cryptography #contests

## Descripción
We received an encrypted message. The modulus is built from primes large enough that factoring them isn’t an option, at least not today. See if you can make sense of the numbers and reveal the flag.Download the [message](https://challenge-files.picoctf.net/c_amiable_citadel/d75bf3f0753b354c1fabcaec0bdeb5902d67448835d57a0b0b268560a19f16a3/message.txt).
## Solución

Aplicamos el ataque de `Coppersmith` simplificado con un programa en python:
```python
from sympy import integer_nthroot

file = open("message.txt", "r");
lines = file.readlines()

n = int(lines[0].split("n =")[1].strip())
e = int(lines[1].split("e =")[1].strip())
c = int(lines[2].split("c =")[1].strip())

m, exact = integer_nthroot(c, e)
# obtenemos m aplicando raiz e-esima

flag = m.to_bytes((m.bit_length() + 7) // 8, 'big').decode()
# convertimos m a texto legible

print("flag:", flag)
```

```bash
┌──(kali㉿kali)-[~/pico/picoMini/Crack_the_Power]
└─$ python ./desencriptar.py
flag: picoCTF{t1ny_e_9b88056f}
```
## Notas adicionales
 Las aplicaciones particulares del método de `Coppersmith` para atacar `RSA` incluyen casos en los que el exponente público _`e`_ es pequeño o cuando se dispone de un conocimiento parcial de un factor primo de la clave secreta.
 En RSA, el cifrado se define como `c = m^e mod n`. Pero si `m^e < n`, entonces `c = m^e` directamente, sin aplicar la operación módulo. Esto permite recuperar `m` simplemente extrayendo la raíz `e`-ésima de `c`.
## Referencias
[Coppersmith's attack - Wikipedia](https://en.wikipedia.org/wiki/Coppersmith's_attack)
[Criptosistema RSA - Wikipedia](https://en.wikipedia.org/wiki/RSA_cryptosystem)
[PicoCTF Writeup — rsa-pop-quiz. Welcome back, CTF enthusiasts! Today’s… | by SoBatista | Medium](https://medium.com/@sobatistacyber/picoctf-writeup-rsa-pop-quiz-b13fbf4c6d2c)
