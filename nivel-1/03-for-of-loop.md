# For-of Loop
## Introducción
En ES6, la construccion for-of permite ciclar sobre objetos iterables, por ejemplo **Arrays**, **Sets** y **Maps**.

##### Protocolos Iterable / Iterator
Un objeto es **Iterable** cuando define una propiedad con el identificador *`[Symbol.iterator]`*. Esta propiedad debe contener una funcion que retorna un **Iterator**.  
Un **Iterator** es un objeto que define un metodo `next()` que retorna a su vez otro objeto con las siguientes propiedades:
- Una propiedad `done` (boolean) que define si la iterración está terminada o no.
- Una propiedad opcional `value` con el siguiente valor en la iteracion ( omitida si `done === true` ).

##### Diferencias con for-in
Las construcciones for-of y for-in son en apariencia similares, pero tiene diferente funcion:
- `for-in` cicla sobre las propiedades de un objeto.
- `for-of` cicla sobre la serie de valores contenidos por un objeto iterable.

### ES6
```
let mylist = ['One', 'Two', 'Three'];
for (let myitem of mylist) {
    console.log(myitem);
}
```

### ES5:
```
var mylist = ['One', 'Two', 'Three'];
for (var i = 0; i < mylist.length; i++) {
    var myitem = mylist[i];
    console.log(myitem);
}
```

### Desafios
**Desafio 1**  
Dado el siguiente Map:   

`var mymap = new Map([['k1','val1'],['k2','val2']]);`  

Imprimir todas sus entradas con el formato `'<clave> -> <valor>`  

**Solución**  
```
for (var [k,v] of mymap) {
    console.log(k + ' -> ' + v);
}
```
**Desafio 2**  
Dado el array:  

`var myarray = ['A', 'B', 'C']`  

Imprimir todos sus elementos con el formato `''<index> -> <valor>`, pero usando un Iterable que retorne los valores ya formateados.

**Solución**  

```
var arrayFormatter = function(origArray) {
	return {
		[Symbol.iterator]() {
			let myIndex = 0;
			return {
				next: function() {
					let isEnd = (myIndex === origArray.length);
					let formattedValue = myIndex + ' -> ' + origArray[myIndex];
					let item = {
						done: isEnd,
						value: formattedValue
					};
					myIndex++;
					return item
				}
			};
		}
	}
};

var myArray = ['A', 'B', 'C'];

for (var fmtVal of arrayFormatter(myArray)) {
	console.log(fmtVal);
}
```  
