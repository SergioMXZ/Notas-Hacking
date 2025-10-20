#notas_hacking #cryptography 
## Descripción

## Solución
Se encriptaba usando la tabla al mismo tiempo que la clave y la flag, al principio pensé que solo era tomar los indices de llave y clave y ese era el carácter, pero después de intentarlo, me di cuenta que esa era la forma de encriptar, para desencriptar había que buscar el carácter en la fila entre sus columnas. pd(como solo son caracteres ordenados podría haber alguna forma de hacerlo sin dos ciclos)
```cpp
#include <bits/stdc++.h>
using namespace std;

char table[26][26];
void createTable() {
    for(int i = 0; i < 26; i ++) {
        for(int j = 0; j < 26; j ++) {
            int tmp = (i+j)% 26;
            table[i][j] = char('A' + tmp);
        }
    }
}

int main() {
    createTable();
    string s; cin >> s;
    string key; cin >> key;
    string ans = "";

    for (int i = 0; i < size(s); i ++) {
        int r = key[i] - 'A';

        for (int c = 0; c < 26; c ++) {
            if (table[r][c] == s[i]) {
                ans += char(c + 'A');
                break;
            }
        }
    }
    cout << ans << endl;
}    
```

```bash
┌──(kali㉿kali)-[~/pico/crypto]
└─$ g++ easy.cpp -o easy.exe

┌──(kali㉿kali)-[~/pico/crypto]
└─$ UFJKXQZQUNB

UFJKXQZQUNB: command not found
┌──(kali㉿kali)-[~/pico/crypto]
└─$ ./easy.exe              

UFJKXQZQUNB
SOLVECRYPTO
CRYPTOISFUN
```
formato:
`picoCTF{CRYPTOISFUN}`
## Notas

## Referencias
