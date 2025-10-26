#notas_hacking #forensic
## Descripción
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/a917f567b9cc0f1a730a7801b309955df4d2234a8114326857b9759e9e5d0453/myNetworkTraffic.pcap) and try to get the flag.
## Solución
después de analizarlos en `wireshark` parecían contener `base64` los paquetes, y con la pista del tiempo si se ordenaba de acuerdo al tiempo y cambiaba a `ascii` lo que resultaba era la flag

```python
from scapy.all import *
from base64 import *

packets = sorted( rdpcap('myNetworkTraffic.pcap'), key=lambda x: x.time)

resultado = []

for p in  packets:
        if p.haslayer(Raw):
                try: resultado.append(base64.b64decode(p.load).decode('ascii'))
                except: 
                        pass

print(''.join(resultado))
```

```bash
┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ python exp.py
ezF0X3c0cw==
cGljb0NURg==
bnRfdGg0dA==
Yt8ksMM=
3psv5C4=
YQEFzIU=
YmhfNHJfOQ==
a23/UbI=
TOGSGg4=
bpzQ0R8=
fQ==
nfu4Vww=
J4auZMY=
ePRXDio=
fjIzQwk=
XThGxuE=
ckBkZLk=
CJr4oDk=
BgJLB0c=
XzM0c3lfdA==
NTlmNTBkMw==
dgV9v0s=

┌──(kali㉿kali)-[~/pico/Tarea3_forensic]
└─$ python exp.py
KG~23C  picoCTF{1t_w4snt_th4t_34sy_tbh_4r_959f50d3}
```
## Notas

## Referencias
