# Operador de propagación

## Introducción

El operador de propagación (`...`) intoducido en ES6 permite expandir los contenidos de un arreglo en situaciones en las que se requieran múltiples elementos o múltiples argumentos.

## Expandir múltiples elementos

Cuando se necesitan múltiples elementos, por ejemplo durante la enumeración de un arreglo literal, se puede emplear el operador de propagación para incluir todos los elementos de otro arreglo sin necesidad de recurrir a los métodos `concat()` o `push()`.

### ES5

```javascript
var arr1 = ['uno', 'dos'];
var arr2 = ['tres'];
var arr3 = ['catorce'];

console.log(arr1.concat(arr2, arr3)); // [ 'uno', 'dos', 'tres', 'catorce' ]
```

### ES6

```javascript
const arr1 = ['uno', 'dos'];
const arr2 = ['tres'];
const arr3 = ['catorce'];

console.log([...arr1, ...arr2, ...arr3]); // [ 'uno', 'dos', 'tres', 'catorce' ]
```

## Desafios

1. << Acá van los desafios, al menos uno por tema si es que se pueda >>
