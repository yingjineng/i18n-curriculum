---
id: cf1111c1c11feddfaeb4bdef
title: Eine Zahl von einer anderen mit JavaScript subtrahieren
challengeType: 1
forumTopicId: 18314
dashedName: subtract-one-number-from-another-with-javascript
---

# --description--

We can also subtract one number from another.

JavaScript verwendet das Symbol `-` für die Subtraktion.

**Beispiel**

```js
const myVar = 12 - 6;
```

`myVar` würde den Wert `6` haben.
# --instructions--

Ändere die `0` so, dass die Differenz `12` ist.

# --hints--

Die Variable `difference` sollte auf `12` gesetzt sein.

```js
assert(difference === 12);
```

Du solltest nur eine Zahl von `45` abziehen.

```js
assert(/difference=45-33;?/.test(__helpers.removeWhiteSpace(__helpers.removeJSComments(code))));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'difference = '+z;})(difference);
```

## --seed-contents--

```js
const difference = 45 - 0;
```

# --solutions--

```js
const difference = 45 - 33;
```
