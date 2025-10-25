#notas_hacking #forensic
## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
## Solución
Entre los paquetes que su puerto destino es el 22, se encuentra un patron en el que en los patrones corresponden a caracteres por ejemplo 5112 es el `chr(112)` que es p, y así van variando, entonces con `scapy` en python automatizamos la extraction de la bandera 
```python
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)
print(flag)

```
`picoCTF{p1LLf3r3d_data_v1a_st3g0}`
## Notas

## Referencias
