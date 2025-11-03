#notas_hacking #cryptography 
## Descripción
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/239/atbash.jpg).****
## Solución
extremos el archivo, con la herramienta `steghide`
```python
┌──(kali㉿kali)-[~/pico/crypto/cp4/hidetosee]
└─$ sudo apt install steighide

┌──(kali㉿kali)-[~/pico/crypto/cp4/hidetosee]
└─$ sudo apt install steighide

┌──(kali㉿kali)-[~/pico/crypto/cp4/hidetosee]
└─$ steghide --extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".

┌──(kali㉿kali)-[~/pico/crypto/cp4/hidetosee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_1u84w779}
```
creamos un programa para descifrar la bandera del `Atbash Cipher`
```cpp
#include <bits/stdc++.h>
using namespace std;

int main(){
    string enc; cin >> enc;

    int atbash[26];
    for (int i = 0, c = 25; i <= 26; i ++, c --)
        atbash[i] = c;

    string flag = "";
    for (auto c: enc) {
        char des;
        if (c == '{' || c == '}' || c == '_')    des = c;
        else if (c >= '0' && c <= '9')           des = c;
        else {
            char minC = (c > 'Z'? 'a':'A');
            des = (atbash[c - minC]) + minC;
        }
        flag += des;
    }
    cout << flag << endl;
}
```
version fácil:
```cpp
else {
	char minC = (c > 'Z'? 'a':'A');
	des = (((c - minC) - 25) * -1) + minC;
}
```

```python
┌──(kali㉿kali)-[~/pico/crypto/cp4/hidetosee]
└─$ g++ exp.cpp -o exp

┌──(kali㉿kali)-[~/pico/crypto/cp4/hidetosee]
└─$ ./exp             
krxlXGU{zgyzhs_xizxp_1u84w779}
picoCTF{atbash_crack_1f84d779}
```
## Notas

## Referencias

