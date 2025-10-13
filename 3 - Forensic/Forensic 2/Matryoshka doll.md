#notas_hacking #forensic
## Descripción
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/5eb456e480e485183c9c1b16952c6eda/dolls.jpg)
## Solución
Nos damos cuenta que puede aver datos binarios dentro de la imagen.
```bash
Red Tone Reproduction Curve     : (Binary data 2060 bytes, use -b option to extract)
Video Card Gamma                : (Binary data 48 bytes, use -b option to extract)
Native Display Info             : (Binary data 62 bytes, use -b option to extract)
Chromatic Adaptation            : 1.04861 0.02332 -0.05034 0.03018 0.99002 -0.01714 -0.00922 0.01503 0.75172
Make And Model                  : (Binary data 40 bytes, use -b option to extract)
Blue Tone Reproduction Curve    : (Binary data 2060 bytes, use -b option to extract)
Green Tone Reproduction Curve   : (Binary data 2060 bytes, use -b option to extract)
```
tiene un zip dentro entonces podríamos usar `unzip`
```
┌──(kali㉿kali)-[~/pico/Forensic3/Matryoshka]
└─$ binwalk dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378956, uncompressed size: 383938, name: base_images/2_c.jpg
651614        0x9F15E         End of Zip archive, footer length: 22
┌──(kali㉿kali)-[~/pico/Forensic3/Matryoshka]
└─$ unzip dolls.jpg         
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg     
```
parece que hay otro dentro, así seguimos hasta encontrar la flag
```bash
┌──(kali㉿kali)-[~/pico/Forensic3/Matryoshka]
└─$ cd base_images 
┌──(kali㉿kali)-[~/pico/Forensic3/Matryoshka/base_images]
└─$ unzip 2_c.jpg  
Archive:  2_c.jpg
warning [2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg     
┌──(kali㉿kali)-[~/pico/Forensic3/Matryoshka/base_images]
└─$ cd base_images 
┌──(kali㉿kali)-[~/…/Forensic3/Matryoshka/base_images/base_images]
└─$ unzip 3_c.jpg
Archive:  3_c.jpg
warning [3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg     
┌──(kali㉿kali)-[~/…/Forensic3/Matryoshka/base_images/base_images]
└─$ cd base_images 
┌──(kali㉿kali)-[~/…/Matryoshka/base_images/base_images/base_images]
└─$ unzip 4_c.jpg
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt                
┌──(kali㉿kali)-[~/…/Matryoshka/base_images/base_images/base_images]
└─$ cat flag.txt                
picoCTF{336cf6d51c9d9774fd37196c1d7320ff}     
```
## Notas

## Referencias
