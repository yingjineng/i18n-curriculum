---
id: 56533eb9ac21ba0edf2244b9
title: Construye cadenas con variables
challengeType: 1
forumTopicId: 16805
dashedName: constructing-strings-with-variables
---

# --description--

A veces necesitarás construir una cadena. Al usar el operador de concatenación (`+`), puedes insertar una o más variables en una cadena que estés construyendo.

Ejemplo:

```js
const ourName = "freeCodeCamp";
const ourStr = "Hello, our name is " + ourName + ", how are you?";
```

`ourStr` tendrá como valor la cadena `Hello, our name is freeCodeCamp, how are you?`.

# --instructions--

Establece `myName` en una cadena igual a tu nombre y construye `myStr` con `myName` entre las cadenas `My name is` y `and I am well!`

# --hints--

`myName` debe establecerse en una cadena de al menos 3 caracteres de largo.

```js
assert(typeof myName !== 'undefined' && myName.length > 2);
```

Debes usar dos operadores `+` para construir `myStr` con `myName` dentro de él.

```js
assert(__helpers.removeJSComments(code).match(/["']\s*\+\s*myName\s*\+\s*["']/g).length > 0);
```

# --seed--

## --after-user-code--

```js
(function(){
  var output = [];
  if(typeof myName === 'string') {
    output.push('myName = "' + myName + '"');
  } else {
    output.push('myName is not a string');
  }
  if(typeof myStr === 'string') {
    output.push('myStr = "' + myStr + '"');
  } else {
    output.push('myStr is not a string');
  }
  return output.join('\n');
})();
```

## --seed-contents--

```js
// Only change code below this line
const myName = "";
const myStr = "";
```

# --solutions--

```js
const myName = "Bob";
const myStr = "My name is " + myName + " and I am well!";
```
