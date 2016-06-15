# Operador de Propagación (`...`)

## Introducción

El operador de propagación (`...`) intoducido en ES6 permite expandir los contenidos de un arreglo en situaciones en las que se requieran múltiples elementos o múltiples argumentos.

## Expandir múltiples elementos

Cuando se necesitan múltiples elementos, por ejemplo durante la enumeración de un arreglo literal, se puede emplear el operador de propagación para incluir todos los elementos de otro arreglo sin necesidad de recurrir a los métodos `concat()` o `push()`.

Comparemos, por ejemplo, al operador de propagación con el uso de `concat()`:

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

## Expandir parámetros en una invocación de función

En el caso de querer enviar los valores de un arreglo como parámetros a una función, se puede emplear el operador de propagación en lugar de tener que recurrir al uso de `apply()`, y funciona incluso en constructores. Por ejemplo:

### ES5
```javascript
var promedios = [6, 7.5, 9, 2, 5.5];
var mejorPromedio = Math.max.apply(null, promedios);
```

### ES6
```javascript
const promedios = [6, 7.5, 9, 2, 5.5];
const mejorPromedio = Math.max(...promedios);
```

## Relacionado: Parámetros Restantes

En la nueva versión del estándar también se define una nueva sintaxis para definir funciones con cantidades variables de parámetros, cuya sintaxis es muy similar a la del operador de propagación. Durante la definición de una función, si su último parámetro está declarado con un nombre precedido por puntos suspensivos (`...`), acumulará los valores de todos los parámetros restantes en la llamada en un arreglo. Esto evita tener que convertir el valor de `arguments` en un arreglo y luego operar sobre él. Veamos un ejemplo:

### ES5
```javascript
function promedio() {
  var numeros = Array.prototype.slice.call(arguments);
  var suma = numeros.reduce(function(acc, value) {
    return acc + value;
    }, 0);
  return suma / numeros.length;
}
```

### ES6
```javascript
function promedio(...numeros) {
  const suma = numeros.reduce(function(acc, value) {
    return acc + value;
  }, 0);
  return suma / numeros.length;
}
```

## Desafios

1. Implementar en ES6 una función `minimoAbsoluto()` que acepte una cantidad cualquiera de arreglos de números y devuelva el valor más bajo entre todos los elementos de sus parámetros.

Solución
```javascript
function minimoAbsoluto(...arreglos) {
  const minimos = arreglos.map(arreglo => Math.min(...arreglo));
  return Math.min(...minimos);
}
```
