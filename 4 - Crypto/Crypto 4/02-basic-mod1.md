#notas_hacking #cryptography 
## Descripción
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/128/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Solución
Creamos un programa para descifrar el mensaje
```python
#include <bits/stdc++.h>
using namespace std;

int main(){
    freopen("message.txt", "r", stdin);

    int num;
    string flag = "picoCTF{";
    while (cin >> num) {
        int mod = num % 37;
        char c;
        if (mod < 26)       c = mod + 'A';
        else if (mod != 36) c = (mod - 26) + '0';
        else                c = '_';
        flag += c;
    }
    cout << flag << "}" << endl;
    return 0;
}
```

```python
┌──(kali㉿kali)-[~/pico/crypto/cp4/basic-mod1]
└─$ g++ exp.cpp -o exp

┌──(kali㉿kali)-[~/pico/crypto/cp4/basic-mod1]
└─$ ./exp             
picoCTF{R0UND_N_R0UND_B6B25531}
```
## Notas

## Referencias


