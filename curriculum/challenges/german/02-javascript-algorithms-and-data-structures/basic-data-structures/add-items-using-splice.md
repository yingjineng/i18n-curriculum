---
id: 587d78b3367417b2b2512b11
title: Füge Elemente mit der splice() Methode hinzu
challengeType: 1
forumTopicId: 301152
dashedName: add-items-using-splice
---

# --description--

Remember in the last challenge we mentioned that `splice()` can take up to three parameters? Well, you can use the third parameter, comprised of one or more element(s), to add to the array. This can be incredibly useful for quickly switching out an element, or a set of elements, for another.

```js
const numbers = [10, 11, 12, 12, 15];
const startIndex = 3;
const amountToDelete = 1;

numbers.splice(startIndex, amountToDelete, 13, 14);
console.log(numbers);
```

Das zweite Auftreten von `12` wird entfernt und wir fügen `13` und `14` an den gleichen Index hinzu. Der `numbers` Array würde jetzt `[ 10, 11, 12, 13, 14, 15 ]` sein.

Hier starten wir mit einem Zahlen-Array. Anschließend übergeben wir Folgendes an `splice()`: Der Index, mit dem Elemente gelöscht werden sollen (3), die Anzahl der zu löschenden Elemente (1), und die verbleibenden Argumente (13, 14) werden am selben Index beginnend eingefügt. Beachte, dass es beliebig viele Elemente geben kann (durch Kommata getrennt), welche dem `amountToDelete` folgen, von denen jedes eingefügt wird.

# --instructions--

Wir haben eine Funktion `htmlColorNames` definiert, die ein Array aus HTML-Farben als Argument verwendet. Ändere die Funktion, indem du `splice()` benutzt, um die ersten zwei Elemente des Arrays zu entfernen und um `'DarkSalmon'` und `'BlanchedAlmond'` an ihre jeweiligen Stellen hinzuzufügen.

# --hints--

`htmlColorNames` sollte `["DarkSalmon", "BlanchedAlmond", "LavenderBlush", "PaleTurquoise", "FireBrick"]` zurückgeben.

```js
assert.deepEqual(
  htmlColorNames([
    'DarkGoldenRod',
    'WhiteSmoke',
    'LavenderBlush',
    'PaleTurquoise',
    'FireBrick'
  ]),
  [
    'DarkSalmon',
    'BlanchedAlmond',
    'LavenderBlush',
    'PaleTurquoise',
    'FireBrick'
  ]
);
```

Die Funktion `htmlColorNames` sollte die Methode `splice()` verwenden.

```js
assert(/.splice/.test(__helpers.removeJSComments(code)));
```

Du solltest nicht`shift()` oder `unshift()` verwenden.

```js
assert(!/shift|unshift/.test(__helpers.removeJSComments(code)));
```

Du solltest keine Array-Klammernotation verwenden.

```js
assert(!/\[\d\]\s*=/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
function htmlColorNames(arr) {
  // Only change code below this line

  // Only change code above this line
  return arr;
}

console.log(htmlColorNames(['DarkGoldenRod', 'WhiteSmoke', 'LavenderBlush', 'PaleTurquoise', 'FireBrick']));
```

# --solutions--

```js
function htmlColorNames(arr) {
  arr.splice(0,2,'DarkSalmon', 'BlanchedAlmond');
  return arr;
}
```
