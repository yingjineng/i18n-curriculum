---
id: cf1111c1c11feddfaeb8bdef
title: Modificare i dati dell'array con gli indici
challengeType: 1
forumTopicId: 18241
dashedName: modify-array-data-with-indexes
---

# --description--

Unlike strings, the entries of arrays are <dfn>mutable</dfn> and can be changed freely, even if the array was declared with `const`.

**Esempio**

```js
const ourArray = [50, 40, 30];
ourArray[0] = 15;
```

`ourArray` ha ora il valore `[15, 40, 30]`.

**Note:** Non ci dovrebbero essere spazi tra il nome dell'array e le parentesi quadre, come in `array [0]`. Anche se JavaScript è in grado di elaborarlo correttamente, questo potrebbe confondere altri programmatori che leggono il tuo codice.

# --instructions--

Modificare i dati memorizzati all'indice `0` di `myArray` a un valore di `45`.

# --hints--

`myArray` dovrebbe ora essere `[45, 64, 99]`.

```js
assert(
  (function () {
    if (
      typeof myArray != 'undefined' &&
      myArray[0] == 45 &&
      myArray[1] == 64 &&
      myArray[2] == 99
    ) {
      return true;
    } else {
      return false;
    }
  })()
);
```

Dovresti usare l'indice corretto per modificare il valore in `myArray`.

```js
assert(
  (function () {
    if (__helpers.removeJSComments(code).match(/myArray\[0\]\s*=\s*/g)) {
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
if(typeof myArray !== "undefined"){(function(){return myArray;})();}
```

## --seed-contents--

```js
// Setup
const myArray = [18, 64, 99];

// Only change code below this line

```

# --solutions--

```js
const myArray = [18, 64, 99];
myArray[0] = 45;
```
