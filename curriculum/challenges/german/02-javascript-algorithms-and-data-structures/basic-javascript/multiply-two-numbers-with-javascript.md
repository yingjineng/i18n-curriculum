---
id: cf1231c1c11feddfaeb5bdef
title: Zwei Zahlen mit JavaScript multiplizieren
challengeType: 1
forumTopicId: 18243
dashedName: multiply-two-numbers-with-javascript
---

# --description--

We can also multiply one number by another.

JavaScript verwendet das Symbol `*` für die Multiplikation von zwei Zahlen.

**Beispiel**

```js
const myVar = 13 * 13;
```

`myVar` würde den Wert `169` haben.

# --instructions--

Ändere die `0` so, dass das Produkt gleich `80` ist.

# --hints--

Die Variable `product` sollte den Wert 80 haben.

```js
assert(product === 80);
```

Du solltest den Operator `*` verwenden.

```js
assert(/\*/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'product = '+z;})(product);
```

## --seed-contents--

```js
const product = 8 * 0;
```

# --solutions--

```js
const product = 8 * 10;
```
