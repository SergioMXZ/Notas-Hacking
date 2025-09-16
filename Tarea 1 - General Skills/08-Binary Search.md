#notas_hacking
# Reto
## Descripción
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses. Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools! You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_atlas/4/challenge.zip)
Additional details will be available after launching your challenge instance.
## Solución
```bash
--descargar--archivo--mirar--como--esta--hecho
┌──(kali㉿kali)-[~/retos/home]
└─$ ssh -p 62745 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Higher! Try again.
Enter your guess: 750
Higher! Try again.
Enter your guess: 875
Lower! Try again.
Enter your guess: 812
Higher! Try again.
Enter your guess: 843
Lower! Try again.
Enter your guess: 827
Lower! Try again.
Enter your guess: 820
Lower! Try again.
Enter your guess: 816
Congratulations! You guessed the correct number: 816
Here's your flag: picoCTF{g00d_gu355_ee8225d0}
Connection to atlas.picoctf.net closed.
```
Se puede encontrar el numero en `O(log(1000))` ósea menos o igual a 10  intentos, utilizando búsqueda binaria "mental": Divides el numero de elementos entre el numero mínimo y máximo, si este numero es mayor descartas todos los numero incluyendo este menores a este mismo, y ahora tu mínimo es el numero anterior mas uno, repites el procedimiento, igual si es menor, descartas de ese número a tu máximo y ahora tu máximo es el numero menos uno.
## Notas

## Referencias
