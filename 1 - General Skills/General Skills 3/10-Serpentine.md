#notas_hacking #general_skills
# Reto
## Descripción
Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/37/serpentine.py)
## Solución
```bash
SergioMXZ-picoctf@webshell:~$ nano serpentine.py 
cambie el codigo para que llame a la funcion que imprime la bandera
SergioMXZ-picoctf@webshell:~$ python serpentine.py 

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b
picoCTF{7h3_r04d_l355_7r4v3l3d_8e47d128}
```
arregle el código para que al elegir la opción b si muestre la bandera 
## Notas
## Referencias
