#notas_hacking #web
# Reto
## Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:58493/) and see what you can discover.
## Solución

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Secure Log In</title>
  </head>
  <body>
    <script src="[guest.js](view-source:http://saturn.picoctf.net:58493/guest.js)"></script>

    <h1>Online Gradebook</h1>
    <button type="button" onclick="continueAsGuest();">Continue as guest</button>
  </body>
</html>
```
`/guest.js`
```js
function continueAsGuest()
{
  window.location.href = '/check.php';
  document.cookie = "isAdmin=0";
}
```
cambie a admin=1 en `/check.php`
## Notas

## Referencias
