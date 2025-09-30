#notas_hacking #web
# Reto
## Descripción
How about trying to match a regular expression The website is running [here](http://saturn.picoctf.net:61755/).
## Solución

De este codding nos damos cuenta que la expression regular que utiliza es `^p.....F!` y guiando nos de la pagina de [regex][https://regexr.com/] nos damos cuenta que comienza con p debe contener F al final y cada punto es cualquier carácter
```javascript
function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}
```
`picoCTF{succ3ssfully_matchtheregex_9080e406}`
## Notas

## Referencias
https://regexr.com/