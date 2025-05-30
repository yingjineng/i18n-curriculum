---
id: cf1111c1c12feddfaeb2bdef
title: Genera números enteros aleatorios dentro de un rango
challengeType: 1
forumTopicId: 18187
dashedName: generate-random-whole-numbers-within-a-range
---

# --description--

Puedes generar un número entero aleatorio en el rango de cero a un número determinado. También puedes elegir un número inferior diferente para este rango.

Llamarás a tu número mínimo `min` y a tu número máximo `max`.

Esta fórmula da un número entero aleatorio en el rango desde `min` hasta `max`. Tómate un momento para leerla e intenta entender lo que este código está haciendo:

```js
Math.floor(Math.random() * (max - min + 1)) + min
```

# --instructions--

Crea una función llamada `randomRange` que tenga un rango `myMin` y `myMax` y devuelva un número entero aleatorio mayor o igual a `myMin`, y es menor o igual a `myMax`.

# --hints--

El número aleatorio más bajo que puede ser generado por `randomRange` debe ser igual a tu número mínimo, `myMin`.

```js
assert(calcMin === 5);
```

El número aleatorio más alto que puede ser generado por `randomRange` debe ser igual a tu número máximo, `myMax`.

```js
assert(calcMax === 15);
```

El número aleatorio generado por `randomRange` debe ser un entero, no un decimal.

```js
assert(randomRange(0, 1) % 1 === 0);
```

`randomRange` debe usar `myMax` y `myMin`, y devolver un número aleatorio en tu rango.

```js
assert(
  (function () {
    if (
      __helpers.removeJSComments(code).match(/myMax/g).length > 1 &&
      __helpers.removeJSComments(code).match(/myMin/g).length > 2 &&
      __helpers.removeJSComments(code).match(/Math.floor/g) &&
      __helpers.removeJSComments(code).match(/Math.random/g)
    ) {
      return true;
    } else {
      return false;
    }
  })()
);
```

# --seed--

## --after-user-code--

```js
var calcMin = 100;
var calcMax = -100;
for(var i = 0; i < 100; i++) {
  var result = randomRange(5,15);
  calcMin = Math.min(calcMin, result);
  calcMax = Math.max(calcMax, result);
}
(function(){
  if(typeof myRandom === 'number') {
    return "myRandom = " + myRandom;
  } else {
    return "myRandom undefined";
  }
})()
```

## --seed-contents--

```js
function randomRange(myMin, myMax) {
  return 0;
}
```

# --solutions--

```js
function randomRange(myMin, myMax) {
  return Math.floor(Math.random() * (myMax - myMin + 1)) + myMin;
}
```
