---
id: cf1111c1c11feddfaeb9bdef
title: Generiere zufällige Brüche mit JavaScript
challengeType: 1
forumTopicId: 18185
dashedName: generate-random-fractions-with-javascript
---

# --description--

Random numbers are useful for creating random behavior.

JavaScript hat eine Funktion `Math.random()`, die eine zufällige Dezimalzahl zwischen `0` (einschließlich) und `1` (ausschließlich) erzeugt. So kann `Math.random()` eine `0` zurückgeben, aber niemals eine `1`.

**Hinweis:** Wie bei <a href="/learn/javascript-algorithms-and-data-structures/basic-javascript/storing-values-with-the-assignment-operator" target="_blank" rel="noopener noreferrer nofollow">Speichern von Werten mit dem Zuweisungsoperator</a> werden alle Funktionsaufrufe aufgelöst, bevor `return` ausgeführt wird, sodass wir den Wert der `Math.random()`-Funktion mittels `return` zurückgeben können.

# --instructions--

Ändere `randomFraction` so, dass es eine Zufallszahl zurückgibt, anstatt `0` zu liefern.

# --hints--

`randomFraction` sollte eine Zufallszahl zurückgeben.

```js
assert(typeof randomFraction() === 'number');
```

Die von `randomFraction` zurückgegebene Zahl sollte eine Dezimalzahl sein.

```js
assert((randomFraction() + '').match(/\./g));
```

Du solltest `Math.random` verwenden, um die zufällige Dezimalzahl zu erzeugen.

```js
assert(__helpers.removeJSComments(code).match(/Math\.random/g).length >= 0);
```

# --seed--

## --after-user-code--

```js
(function(){return randomFraction();})();
```

## --seed-contents--

```js
function randomFraction() {

  // Only change code below this line

  return 0;

  // Only change code above this line
}
```

# --solutions--

```js
function randomFraction() {
  return Math.random();
}
```
