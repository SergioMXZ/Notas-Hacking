#notas_hacking
# Reto
## Descripción
How well can you perfom basic binary operations?
Start searching for the flag here `nc titan.picoctf.net 56952`
## Solución
```bash
┌──(kali㉿kali)-[~/retos]
└─$ nc titan.picoctf.net 56952

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 00110110
Binary Number 2: 10101011

Question 1/6:
Operation 1: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 01010101     
Correct!

Question 2/6:
Operation 2: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00100010
Correct!

Question 3/6:
Operation 3: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10111111
Correct!

Question 4/6:
Operation 4: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11011001
Incorrect. Try again
Enter the binary result: 11100001
Correct!

Question 5/6:
Operation 5: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 01101100
Correct!

Question 6/6:
Operation 6: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10100001001010
Incorrect. Try again
Enter the binary result: 10010000010010
Correct!

Enter the results of the last operation in hexadecimal: 2412

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d6f8047e}
```
La solución era obvio menos la que involucraba `*` y conversiones en donde use python
```bash
┌──(kali㉿kali)-[~/retos]
└─$ python
Python 3.13.7 (main, Aug 20 2025, 22:17:40) [GCC 14.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0b00110110 * 0b10101011
9234
>>> bin(9234)
'0b10010000010010'
>>> hex(0b10010000010010)
'0x2412'
```
## Notas

## Referencias
