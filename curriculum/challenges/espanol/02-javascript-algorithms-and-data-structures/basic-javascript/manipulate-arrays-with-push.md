---
id: 56bbb991ad1ed5201cd392cb
title: Manipular arreglos con el método push
challengeType: 1
forumTopicId: 18237
dashedName: manipulate-arrays-with-push
---

# --description--

Una forma sencilla de añadir datos al final de un arreglo es mediante el método `push()`.

El método `push()` toma uno o más <dfn>arguments</dfn> y los añade al final del arreglo, en el orden en que aparecen. Devuelve la nueva longitud del arreglo.

Ejemplos:

```js
const arr1 = [1, 2, 3];
arr1.push(4, 5);

const arr2 = ["Stimpson", "J", "cat"];
arr2.push(["happy", "joy"]);
```

`arr1` ahora tiene el valor `[1, 2, 3, 4, 5]` y `arr2` tiene el valor `["Stimpson", "J", "cat", ["happy", "joy"]]`.

# --instructions--

Empuja `["dog", 3]` al final de la variable `myArray`.

# --hints--

`myArray` debe ser igual a `[["John", 23], ["cat", 2], ["dog", 3]]`.

```js
assert(
  (function (d) {
    if (
      d[2] != undefined &&
      d[0][0] == 'John' &&
      d[0][1] === 23 &&
      d[2][0] == 'dog' &&
      d[2][1] === 3 &&
      d[2].length == 2
    ) {
      return true;
    } else {
      return false;
    }
  })(myArray)
);
```

# --seed--

## --after-user-code--

```js
(function(z){return 'myArray = ' + JSON.stringify(z);})(myArray);
```

## --seed-contents--

```js
// Setup
const myArray = [["John", 23], ["cat", 2]];

// Only change code below this line

```

# --solutions--

```js
const myArray = [["John", 23], ["cat", 2]];
myArray.push(["dog",3]);
```
