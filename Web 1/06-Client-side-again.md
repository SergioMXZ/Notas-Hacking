#notas_hacking
# Reto
## Descripción
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/6353/` ([link](https://jupiter.challenges.picoctf.org/problem/6353/)) or http://jupiter.challenges.picoctf.org:6353
## Solución
```bash
["0a029}", "_again_5", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"]

"0a029}"             -> --final de la bandera
"_again_5"           -> --alguna parte de la bandera
"this"               -> es una palabra reservada
"Password Verified"  -> un mensaje que se imprime
"Incorrect password" -> un mensaje que se imprime
"getElementById"     -> es una pabra reservada
"value"              -> es una pabra reservada
"substring"          -> es una palabra reservada
"picoCTF{"           -> --inicio de la bandera
"not_this"           -> --alguna parte de la bandera
```

`"picoCTF{"`+`"not_this"`+`"_again_5"`+`"0a029}"` <- o -> `"picoCTF{"`+`"_again_5"`+`"not_this"`+`"0a029}"`
`picoCTF{not_this_again_50a029}`
## Notas

## Referencias
[jsnice.org][http://jsnice.org/] - formateo de `JAVASCRIPT