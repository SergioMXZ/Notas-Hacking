#notas_hacking #forensic
# Reto
## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.
## Solución
usamos la herramienta `whireshark` para ver el archivo con la extension de captura de paquetes `.pcap`
```bash
┌──(kali㉿kali)-[~/pico/forensics]
└─$ wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
--2025-10-01 18:34:47--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                 100%[===========================================>] 233.84K   915KB/s    in 0.3s    

2025-10-01 18:34:48 (915 KB/s) - ‘capture.pcap’ saved [239455/239455]
┌──(kali㉿kali)-[~/pico/forensics]
└─$ wireshark capture.pcap & 
[1] 4893
```
encontramos la llave entre con el protocolo `UDP` de `10.0.0.2` y `10.0.0.12`
`picoCTF{StaT31355_636f6e6e}`
## Notas
`.pcap`- como los archivos que contienen datos de captura de paquetes de red
## Referencias
