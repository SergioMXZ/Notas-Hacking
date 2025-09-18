#notas_hacking
# Reto
## Descripción
Can you break into this super secure portal? https://jupiter.challenges.picoctf.org/problem/29835/ (link) or http://jupiter.challenges.picoctf.org:29835
## Solución
Inspeccionamos el código y nos damos cuenta que la `flag` esta en desorden siendo comparada con la contraseña que entra, copiamos esta parte a un archivo `input.txt` y creamos un código que lea estas líneas y con una expresión regular simple guardamos la información relevante en variables con las que dependiendo el caso asignamos un valor que es el orden que tienen y el fragmento de bandera a un vector de pares de un enteros y un string, luego ordenamos estos pares y los imprimimos para dar con la llave. --es mas fácil organizarlas manualmente :\
```bash            
┌──(kali㉿kali)-[~/retos]
└─$ cat input.txt
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '723c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_7') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'e}') {
┌──(kali㉿kali)-[~/retos]
└─$ nano flag.cpp       
┌──(kali㉿kali)-[~/retos]
└─$ ./flag       
picoCTF{no_clients_plz_7723ce}
```
Código en `c++`
```cpp
#include <bits/stdc++.h>
using namespace std;
#define em emplace_back
int main(){
	vector<pair<int, string>> flag;
	freopen("input.txt", "r", stdin);
	int i = 8;
	while (i --){
		char s[10], s2[10], res[10];
		scanf(" if (checkpass.substring(%[^,], %[^)]) == '%[^']') {", s, s2, res);
		// printf("%s, %s, %s\n", s, s2, res);
		// if      (s[0] == '0')         flag.em(0, string(res));
		// else if (!strcmp(s, "split")) flag.em(1, string(res));
		// else                          flag.em((int)s[6], string(res));
		flag.em(s[0] == '0'? 0 : !strcmp(s, "split")? 1 : (int)s[6], string(res)); /*forma reducida*/
	}
	sort(flag.begin(), flag.end());
	for (auto [n, f] : flag) cout << f;
	cout << "\n";
}
```
## Notas
## Referencias
