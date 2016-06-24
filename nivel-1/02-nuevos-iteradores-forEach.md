# ForEach

## Introducción

En ES6, la construccion ForEach() permite ciclar sobre objetos iterables, por ejemplo **Set** y **Map**.

### Anterior a ES5:

Se podia iterar en arreglos usando:

```
var arr = ['a', 'b', 'c'];
for (var i=0; i<arr.length; i++) {
    var elem = arr[i];
    console.log(elem);
}
```

### ES5:

En ES5, se tiene la opción de usar el metodo del Array : forEach()

```
arr.forEach(function (elem) {
    console.log(elem);
});
```

### ES6

En ES6,se puede iterar en arreglos usando el nuevo método entries() y desestructuración.

```
Índice y el valor de cada elemento de la matriz,
for (let [index, elem] of arr.entries()) {
    console.log( [index,'.',elem].join('') );
}
```

### Set,Map usando forEach()

El método forEach() ejecuta una funcion por cada llave/valor del objeto Map. y usa una funcion de callback una vez por cada llave que exista.No ejecuta por llaves que hayan sido borradas.Sin embargo, ejecuta para valores presentes aun siendo undefined.

callback es invocada con tres argumentos:

value,key,object(map)

**Iterar sobre Map**

```
var map = new Map();
map.set('foo', 1);
map.set('bar', {});
map.set('baz', undefined);

map.forEach( function (value, key, map) {
           console.log(key+ ' ' +value);
        }
);
```

No existe llaves en objetos Set, Sin embargo , los 2 primeros argumentos contenidos en el Set,son para hacer consistente la funcion callback con el método forEach del mapa y el Array,

**Iterar sobre Set**

```
var set = new Set();
set.add('foo');
set.add('bar');
set.add(undefined);

set.forEach( function (value, key, set) {
           console.log(key+ ' ' +value);
  });
```

## forEach() & desestructuración

### Qué es una asignación de desestructuración?

Las asignaciones de desestructuración te permiten asignar las propiedades de un arreglo o un objeto a variables, usando una sintaxis similar a la utilizada con valores literales. Esta sintaxis puede ser extremadamente breve, al mismo tiempo exhibiendo más claridad que con el proceso tradicional para acceder propiedades.

Sin desestructuración, tendrías que acceder los primeros tres elementos de un arreglo de la siguiente manera:

```
var first = someArray[0],
      second = someArray[1],
      third = someArray[2];
```

Con desestructuración, el código equivalente es más conciso y legible:

```
var [first, second, third] = someArray;
```

Es probable que la mayoría de las veces se utilize for-of pero el método forEach Array () también se beneficia de la desestructuración. O mejor dicho, su callback lo hace.

Primer ejemplo: la desestructuración de arreglos en un arreglo.

```
const items = [ ['foo', 1], ['bar', 3] ];
items.forEach(([word, count]) => {
    console.log([word,' ',count].join(''));
});
```

Segundo ejemplo: example: la desestructuración de objetos en un arreglo.

```
const items = [
    { word:'foo', count:1 },
    { word:'bar', count:3 },
];
items.forEach(({word, count}) => {
    console.log([word,' ',count].join(''));
});
```

### Desafíos

**Desafío 1**<br>
Dado el siguiente Array:

`const arr= [100,99,98]`

Imprimir todas sus entradas con el formato `'<index> -> <valor>`

**Solución**

```
for (let [index, elem] of arr.entries()) {
    console.log( [index,'->',elem].join('') );
}
```

**Desafío 2**<br>
Dado el siguiente Array:

`const items = [ { word:'foo', count:1 }, { word:'bar', count:3 }, ];`

Imprimir la suma de todos objetos con el formato `Total: N`

**Solución**

```
let items = [ ['foo', 1], ['bar', 3] ],
      sum = 0;
items.forEach(([word, count]) => {
    sum += count;
});
console.log(['Total: ',sum].join(''));
```
