#notas_hacking #web
# Reto
## Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:50672/) and see what you can discover.
## Solución

```html
<!DOCTYPE html>
...
    <script src="[secure.js](view-source:http://saturn.picoctf.net:50672/secure.js)"></script>
    
    <p id='msg'></p>
    
    <form hidden action="[admin.php](view-source:http://saturn.picoctf.net:50672/admin.php)" method="post" id="hiddenAdminForm">
      <input type="text" name="hash" required id="adminFormHash">
    </form>
...
```
view-source:http://saturn.picoctf.net:50672/secure.js
```js
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

`picoCTF{j5_15_7r4n5p4r3n7_a8788e61}`
## Notas

## Referencias
