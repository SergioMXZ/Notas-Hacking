#notas_hacking #cryptography 
## Descripción
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 39894`.
## Solución
Había que descifrarlo por frecuencia de palabras y letras, ayudándonos de la pagina de `subtitution solver`, es  similar a el ROT pero aquí eligen al azar que letra asigna a que letra, por lo que una fuerza bruta es mas complicada:
abcdefghijklmnopqrstuvwxyz     This clear text ...  
**cqrydtjbihvpeuzsfoxgnklmwa**  ... maps to this cipher text
```
---------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_agflcgtyue
---------------------------------------------------------------------
```
y parece que tenia un formato inusual entonces la llave final seguía siendo:
`frequency_is_c_over_lambda_agflcgtyue`
## Notas

## Referencias
https://www.guballa.de/substitution-solver