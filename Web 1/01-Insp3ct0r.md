#notas_hacking
# Reto
## Descripción
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/9670/` ([link](https://jupiter.challenges.picoctf.org/problem/9670/)) or http://jupiter.challenges.picoctf.org:9670
## Solución
```html
<!doctype html>
<html>
...
	<p>I used these to make this site: <br/>
	  HTML <br/>
	  CSS <br/>
	  JS (JavaScript)
	</p>
	<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
      </div>
    </div>
  </body>
</html>
```
```css
...
.tablink:hover {
    background-color: #777;
}
.tabcontent {
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}
#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }
/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
```
```js
function openTab(tabName,elmnt,color) {
    var i, tabcontent, tablinks;
    tabcontent = document.getElementsByClassName("tabcontent");
    for (i = 0; i < tabcontent.length; i++) {
	tabcontent[i].style.display = "none";
    }
    tablinks = document.getElementsByClassName("tablink");
    for (i = 0; i < tablinks.length; i++) {
	tablinks[i].style.backgroundColor = "";
    }
    document.getElementById(tabName).style.display = "block";
    if(elmnt.style != null) {
	elmnt.style.backgroundColor = color;
    }
}
window.onload = function() {
    openTab('tabintro', this, '#222');
}
/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?2e7b23e3} */
```
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}
## Notas
**http**:
- `Servidor` -> Respuesta
- `Cliente`   -> Solicitud
- `Cookies`   -> Chache del navegador

**robots.txt**:
- Archivo de texto simple que se coloca en el directorio raíz, comunica con los `robots` de motor de búsqueda para indicar donde pueden explorar y donde no, como un semáforo para los `bots` de los rastreadores como el de Google que indexa paginas para su buscador
## Referencias
