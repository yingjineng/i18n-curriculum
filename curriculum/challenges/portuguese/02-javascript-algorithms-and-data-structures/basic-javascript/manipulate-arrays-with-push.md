---
id: 56bbb991ad1ed5201cd392cb
title: Manipular arrays com o método push
challengeType: 1
forumTopicId: 18237
dashedName: manipulate-arrays-with-push
---

# --description--

An easy way to append data to the end of an array is via the `push()` method.

O método `push()` recebe um ou mais <dfn>argumentos</dfn> e os insere no final do array, na ordem em que eles aparecerem. Ele retorna o novo comprimento do array.

Exemplos:

```js
const arr1 = [1, 2, 3];
arr1.push(4, 5);

const arr2 = ["Stimpson", "J", "cat"];
arr2.push(["happy", "joy"]);
```

`arr1` agora tem o valor de `[1, 2, 3, 4, 5]` e `arr2` tem o valor de `["Stimpson", "J", "cat", ["happy", "joy"]]`.

# --instructions--

Empurre `["dog", 3]` para o final da variável `myArray`.

# --hints--

`myArray` agora deve ser igual a `[["John", 23], ["cat", 2], ["dog", 3]]`.

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
