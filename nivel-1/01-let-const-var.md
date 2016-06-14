# Let, Const, y Var

## Introducción

Como primera mejora a la especificación vamos a introducirlos a las nuevas 
maneras de declarar variables.

## let

let nos permite declarar variables con alcance de bloque, declaración o 
expresión donde se utilice. La variable puede ser reasignada.

En la siguiente comparación veremos como la definición de la variable de control i
en una estructura de control for solo tiene alcance local en ES6.

### ES5
```javascript
for( var i = 0 ; i < 10 ; i ++)
    console.log(i); // La salida sera 0,1,2,..., 9
console.log(i); // La salida sera 10
```

### ES6
```javascript
for( let i = 0 ; i < 10 ; i ++)
    console.log(i); // La salida sera 0,1,2,..., 9
console.log(i); // La salida sera "Uncaught ReferenceError: i is not defined"
```

## var

var mantiene su signficado de palabra reservada para la declaración de 
variables y permite ser reasignada, aunque ahora pasa a ser la forma de 
declarar variables de alcance global.

En el siguiente ejemplo mostremos como la definción de una variable dentro
de un bloque solo tiene visibilidad dentro de el bloque donde esta definida.

### ES5
```javascript
    var temporal = true;
    if( temporal ){
      var emacs = "ES6";
    }
    console.log('El valor de emacs es: ' + emacs);
```

### ES6
```javascript
    let temporal = true;
    if( temporal ){
      let emacs = "ES6";
    }
    console.log('El valor de emacs es: ' + emacs);
```

## const

const nos permitira de ahora en más la declaración de constantes o en 
otras palabras, la variable no podra ser reasignada. Cualquier intento 
de asignación posterior a la declaración de la constante se penalizara 
con una excepción. En el caso de las declaraciones de objeto, lo que es 
constante es la referencia: una vez que se apunta a un objeto, no puede 
apuntarse a otro. Aun así, los atributos del objeto pueden cambiar. 
Por ejemplo en ES6:

```javascript
const objeto = {
    texto: "esto es un objeto"
}

objeto = {
    texto: "y esto es otro objeto"
} // NO es válido

objeto.texto = "esto es un cambio válido de un atributo, pero el mismo objeto" // ES válido
```

### ES5
```javascript
//  only in ES5 through the help of object properties
//  and only in global context and not in a block scope
Object.defineProperty(typeof global === "object" ? global : window, "PI", {
    value:        3.141593,
    enumerable:   true,
    writable:     false,
    configurable: false
})
PI > 3.0;
```

### ES6
```javascript
const PI = 3.141593;
PI > 3.0;
```

## Desafios

1. Corrija los errores en el siguiente bloque de codigo:

```javascript
const calcularArea = function(radio){
    var PI = 3.141593;
    const area = ( radio * 2 ) 
    area = area * PI;
    return area;
}
console.log('El valor de PI es ' + PI + ' y de un circulo con radio ' +  3  + 
            ' el valor del area es: ' + calcularArea(3) );

```
Solucion:
```javascript
const PI = 3.141593;

const calcularArea = function(radio){    
    let area = ( radio * 2 ) 
    area = area * PI;
    return area;
}
console.log('El valor de PI es ' + PI + ' y de un circulo con radio ' + 3  + 
            ' el valor del area es: ' + calcularArea(3) );

```