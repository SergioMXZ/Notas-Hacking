#notas_hacking #web
# Reto
## Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:58107/) and see what you can discover.
## Solución

view-source:http://saturn.picoctf.net:58107/script.js
```js
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_df589022}
```
view-source:http://saturn.picoctf.net:58107/style.css
```css
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */
```
`picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}`
## Notas

`Include directive` - indica a un procesador de archivos de texto que reemplace el texto de la directiva con el contenido de un archivo especificado.
## Referencias
Include directive - [wiki definition][https://en-m-wikipedia-org.translate.goog/wiki/Include_directive?_x_tr_sl=en&_x_tr_tl=es&_x_tr_hl=es-419]