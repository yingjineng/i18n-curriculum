---
id: bd7993c9ca9feddfaeb7bdef
title: Dividieren einer Dezimalzahl durch eine andere mit JavaScript
challengeType: 1
forumTopicId: 18255
dashedName: divide-one-decimal-by-another-with-javascript
---

# --description--

Now let's divide one decimal by another.

# --instructions--

Ändere `0.0`, so dass `quotient` gleich `2.2` wird.

# --hints--

Die Variable `quotient` sollte gleich `2.2` sein.

```js
assert(quotient === 2.2);
```

Verwende den Operator `/`, um 4,4 durch 2 zu teilen.

```js
assert(/4\.40*\s*\/\s*2\.*0*/.test(__helpers.removeJSComments(code)));
```

Die Quotientenvariable sollte nur einmal zugewiesen werden

```js
assert(__helpers.removeJSComments(code).match(/quotient\s*=/g).length === 1);
```

# --seed--

## --seed-contents--

```js
const quotient = 0.0 / 2.0; // Change this line
```

# --solutions--

```js
const quotient = 4.4 / 2.0;
```
