#notas_hacking #web
# Reto
## Descripción
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:56901/).
## Solución
`/secret/`
```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="[hidden/file.css](view-source:http://saturn.picoctf.net:56901/secret/hidden/file.css)" />
  </head>

  <body>
    <h1>Finally. You almost found me. you are doing well</h1>
    <img src="[https://media1.tenor.com/images/0a6aff9f825af62c05adfbd75039cc7b/tenor.gif?itemid=4648337](view-source:https://media1.tenor.com/images/0a6aff9f825af62c05adfbd75039cc7b/tenor.gif?itemid=4648337)" alt="Something Like That GIF - Andy Parksandrecreation Wtf GIFs" style="max-width: 833px; background-color: rgb(151, 121, 85);" width="833" height="937.125">
  </body>
</html>
```
`/secret/hidden/`
```html
...
              <input type="hidden" name="db" value="superhidden/xdfgwd.html" />
...
```
`/secret/hidden/superhidden/`
```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="[mycss.css](view-source:http://saturn.picoctf.net:56901/secret/hidden/superhidden/mycss.css)" />
  </head>

  <body>
    <h1>Finally. You found me. But can you see me</h1>
    <h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_39849bcf}</h3>
  </body>
</html>
```
## Notas

## Referencias
