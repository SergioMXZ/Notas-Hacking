#notas_hacking #web
# Reto
## Descripción
There is some interesting information hidden around this site [http://mercury.picoctf.net:44070/](http://mercury.picoctf.net:44070/). Can you find it?
## Solución
en el `html`
```html
</p> <!-- Here's the first part of the flag: picoCTF{t --> </div>
```
en el `css`
```css
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```
en el `/robots.txt`
```txt
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```
en el `.htaccess`
```txt
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```
en el `.DS_Store`
```txt
Congrats! You completed the scavenger hunt. Part 5: _7a46d25d}
```

`picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}`
## Notas
## Referencias
[Apache HTTP Server Tutorial: .htaccess files - Apache HTTP Server Version 2.4](https://httpd.apache.org/docs/2.4/en/howto/htaccess.html) - Los archivos .htaccess proporcionan una manera de realizar cambios de configuración por directorio.
[.DS_Store - Wikipedia](https://en.wikipedia.org/wiki/.DS_Store) - es un archivo que almacena atributos personalizados de la carpeta que lo contiene, como la posición de los iconos o la imagen de fondo.