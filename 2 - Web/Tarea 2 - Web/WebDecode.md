#notas_hacking #web
# Reto
## Descripción
Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:57412/) to find the flag
## Solución
`/about.html`
```html
...
  <section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMTBmOTM3NmZ9">
   <h1>
    Try inspecting the page!! You might find it there
...
```
`cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMTBmOTM3NmZ9` a `base64`
es = `picoCTF{web_succ3ssfully_d3c0ded_10f9376f}`
## Notas

## Referencias
