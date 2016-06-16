# For-of Loop
### Introducción
En ES6, la construccion for-of permite ciclar sobre objetos iterables, por ejemplo **Arrays**, **Sets** y **Maps**.

Ejemplo:
```
let mylist = ['One', 'Two', 'Three'];
for (let myitem of mylist) {
    console.log(myitem);
}
```

Codigo equivalente en ES5:
```
var mylist = ['One', 'Two', 'Three'];
for (var i = 0; i < mylist.length; i++) {
    var myitem = mylist[i];
    console.log(myitem);
}
```

#### Protocolos Iterable / Iterator

### Diferencias con for-in
Las construcciones for-of y for-in son en apariencia similares, pero tiene diferente funcion:
- `for-in` cicla sobre las propiedades de un objeto.
- `for-of` cicla sobre la serie de valores contenidos por un objeto iterable.

### Desafios

