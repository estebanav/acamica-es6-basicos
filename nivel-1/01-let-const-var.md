# Let, Const, y Var

## Introducción

Como primera mejora la especificación vamos a introducirlos a las nuevas maneras de declarar variables.

## var

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

## let

let nos permite declarar variables con alcance de bloque, declaración o expresión donde se utilice.

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

## const

const nos permitira de ahora en más la declaración de constantes. Cualquier intento de asignación posterior a la declaración
de la constante se penalizara con una excepción.

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