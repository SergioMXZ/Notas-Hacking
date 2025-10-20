#notas_hacking #cryptography 
## Descripción
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?
## Solución
Se uso una encriptación en donde intercambias la letra por el numero de su posición en el alfabeto: a: 1, b:2 ... z: 26, para obtener el mensaje cree un código en c++ que cambia este valor por su respectiva letra
``` cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    freopen("input.txt", "r", stdin);
    string s = "";
    int n;
    while (cin >> n) {
         s += 'a' + (n-1);
    }
    cout << s << endl;
}
```
le quite los símbolos `{ }` para no manejar los en el código
```bash
┌──(kali㉿kali)-[~/pico/crypto]
└─$ cat input.txt       
16 9 3 15 3 20 6 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14

┌──(kali㉿kali)-[~/pico/crypto]
└─$ ./the_numbers.exe  
picoctfthenumbersmason
```
la formateamos:
`picoCTF{thenumbersmason}`
## Notas

## Referencias
