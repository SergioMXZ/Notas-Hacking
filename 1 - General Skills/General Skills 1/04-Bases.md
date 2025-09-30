#notas_hacking #general_skills
# Reto
## Descripción
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.
## Solución
Cyberchef
Formula: From Base64
l3arn_th3_r0p35

```bash
>>> import base64
>>> base64.b64decode("bDNhcm5fdGgzX3IwcDM1").decode()
'l3arn_th3_r0p35'
```
## Notas
base64 - en Python esta librería ayuda a manejar y convertir código en base 64 a otro
## Referencias
