---
id: cf1111c1c11feddfaeb6bdef
title: Dividieren einer Zahl durch eine andere mit JavaScript
challengeType: 1
forumTopicId: 17566
dashedName: divide-one-number-by-another-with-javascript
---

# --description--

We can also divide one number by another.

JavaScript verwendet das Symbol `/` für die Division.

**Beispiel**

```js
const myVar = 16 / 2;
```

`myVar` hat jetzt den Wert `8`.
# --instructions--

Ändere die `0` so, dass der `quotient` gleich `2` ist.

# --hints--

Die Variable `quotient` sollte 2 sein.

```js
assert(quotient === 2);
```

Du solltest den Operator `/` verwenden.

```js
assert(/\d+\s*\/\s*\d+/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'quotient = '+z;})(quotient);
```

## --seed-contents--

```js
const quotient = 66 / 0;
```

# --solutions--

```js
const quotient = 66 / 33;
```
