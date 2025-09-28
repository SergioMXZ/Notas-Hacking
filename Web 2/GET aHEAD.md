#notas_hacking
# Reto
## Descripción
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:15931/](http://mercury.picoctf.net:15931/)
## Solución
enviar una solicitud HEAD
 ```bash
┌──(kali㉿kali)-[~/retos]
└─$ curl -I HEAD http://mercury.picoctf.net:15931/index.php               
curl: (6) Could not resolve host: HEAD
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_82880908}
Content-type: text/html; charset=UTF-8
 ```
## Notas
`HEAD` - Solicita una respuesta idéntica a una solicitud GET, pero sin un cuerpo de respuesta.
## Referencias
https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods
