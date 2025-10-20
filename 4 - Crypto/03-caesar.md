#notas_hacking #cryptography 
## Descripción

## Solución
Con fuerza bruta encontré que tenían 4 rotaciones, en un código de c++ aplique todas las rotaciones:
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int r = 26;
    string s; cin >> s;
    string ans;

    while (r --) {
        ans = "";
        for(char c : s) {
            int tmp;

            tmp = c - 'a';
            tmp += r;
            tmp %= 26;
            tmp += 'a';

            ans += char(tmp);
        }
        cout << "r=" << r << ": "<< ans << endl;
    }
}
```
resultado:
```bash
┌──(kali㉿kali)-[~/pico/crypto]
└─$ cat ciphertext              
picoCTF{ynkooejcpdanqxeykjrbdofgkq}                                                                                                                 
┌──(kali㉿kali)-[~/pico/crypto]
└─$ g++ caesar.cpp -o caesar.exe
                                                                                                                 
┌──(kali㉿kali)-[~/pico/crypto]
└─$ ./caesar.exe                
ynkooejcpdanqxeykjrbdofgkq
r=25: xmjnndiboczmpwdxjiqacnefjp
r=24: wlimmchanbylovcwihpzbmdeio
r=23: vkhllbgzmaxknubvhgoyalcdhn
r=22: ujgkkafylzwjmtaugfnxzkbcgm
r=21: tifjjzexkyvilsztfemwyjabfl
r=20: sheiiydwjxuhkrysedlvxizaek
r=19: rgdhhxcviwtgjqxrdckuwhyzdj
r=18: qfcggwbuhvsfipwqcbjtvgxyci
r=17: pebffvatgurehovpbaisufwxbh
r=16: odaeeuzsftqdgnuoazhrtevwag
r=15: nczddtyrespcfmtnzygqsduvzf
r=14: mbyccsxqdrobelsmyxfprctuye
r=13: laxbbrwpcqnadkrlxweoqbstxd
r=12: kzwaaqvobpmzcjqkwvdnparswc
r=11: jyvzzpunaolybipjvucmozqrvb
r=10: ixuyyotmznkxahoiutblnypqua
r=9: hwtxxnslymjwzgnhtsakmxoptz
r=8: gvswwmrkxlivyfmgsrzjlwnosy
r=7: furvvlqjwkhuxelfrqyikvmnrx
r=6: etquukpivjgtwdkeqpxhjulmqw
r=5: dspttjohuifsvcjdpowgitklpv
r=4: crossingtherubiconvfhsjkou
r=3: bqnrrhmfsgdqtahbnmuegrijnt
r=2: apmqqglerfcpszgamltdfqhims
r=1: zolppfkdqeboryfzlkscepghlr
r=0: ynkooejcpdanqxeykjrbdofgkq
```
Resulto en que la bandera es el 4:
`crossingtherubiconvfhsjkou`
## Notas

## Referencias
