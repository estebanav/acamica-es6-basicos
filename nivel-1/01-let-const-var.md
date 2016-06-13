# Let, Const, y Var

## Introducción

Como primera mejora la especificación vamos a introducirlos a las nuevas 
maneras de declarar variables.

## let

let nos permite declarar variables con alcance de bloque, declaración o 
expresión donde se utilice. La variable puede ser reasignada.

### ES5
```javascript
for( var i = 0 ; i < 10 ; i ++)
    console.log(i);
console.log(i);
```

### ES6
```javascript
for( let i = 0 ; i < 10 ; i ++)
    console.log(i);
console.log(i);
```

## var

var mantiene su signficado de palabra reservada para la declaración de 
variables y permite ser reasignada, aunque ahora pasa a ser la forma de 
declarar variables de alcance global.

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
      let emacs = "ES6";dale to
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
Por ejemplo:

```javascript
const objeto = {
    texto: "esto es un objeto"
}

objeto = {
    texto: "y esto es otro objeto"
} // NO ES VÁLIDO

objeto.texto = "esto es un cambio válido de un atributo, pero el mismo objeto" // VÁLIDO
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

1. << Acá van los desafios, al menos uno por tema si es que se pueda >>
