#notas_hacking #cryptography 
## Descripción
In RSA d is a lot bigger than e, why don't we use d to encrypt instead of e? Connect with `nc jupiter.challenges.picoctf.org 57464`.
## Solución
Parece ser que usaron la `d` en lugar de la `e`, porque la e es mas grande de lo usual, entonces en lugar de cifrar vamos a descifrar como si fuera la llave privada
```python
c = 8301447962..
n = 91746432...
#e = 856889...

e = 65537
n = pow(c, e, n)

flag = bytes.fromhex( hex(n)[2:] ).decode()
print(flag)
_______________________________________________
┌──(kali㉿kali)-[~/pico/crypto]
└─$ /bin/python /home/kali/pico/crypto/b00tl3gRSA2/s4.py
picoCTF{bad_1d3a5_2152720}
```
## Notas

## Referencias
