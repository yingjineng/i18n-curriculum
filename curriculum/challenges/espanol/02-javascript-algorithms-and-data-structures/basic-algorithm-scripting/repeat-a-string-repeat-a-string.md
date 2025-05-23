---
id: afcc8d540bea9ea2669306b6
title: Repite una cadena repite una cadena
challengeType: 1
forumTopicId: 16041
dashedName: repeat-a-string-repeat-a-string
---

# --description--

Repite una cadena dada `str` (primer argumento) por un número (`num`) de veces (segundo argumento). Devuelve una cadena vacía si `num` no es un número positivo. For the purpose of this challenge, do _not_ use the built-in `.repeat()` method.

# --hints--

`repeatStringNumTimes("*", 3)` debe devolver la cadena `***`.

```js
assert.strictEqual(repeatStringNumTimes('*', 3), '***');
```

`repeatStringNumTimes("abc", 3)` debe devolver la cadena `abcabcabc`.

```js
assert.strictEqual(repeatStringNumTimes('abc', 3), 'abcabcabc');
```

`repeatStringNumTimes("abc", 4)` debe devolver la cadena `abcabcabcabc`.

```js
assert.strictEqual(repeatStringNumTimes('abc', 4), 'abcabcabcabc');
```

`repeatStringNumTimes("abc", 1)` debe devolver la cadena `abc`.

```js
assert.strictEqual(repeatStringNumTimes('abc', 1), 'abc');
```

`repeatStringNumTimes("*", 8)` debe devolver la cadena `********`.

```js
assert.strictEqual(repeatStringNumTimes('*', 8), '********');
```

`repeatStringNumTimes("abc", -2)` debe devolver una cadena vacía (`""`).

```js
assert.isEmpty(repeatStringNumTimes('abc', -2));
```

El método incorporado `repeat()` no debe ser utilizado.

```js
assert.notMatch(__helpers.removeJSComments(code), /\.repeat/g);
```

`repeatStringNumTimes("abc", 0)` debe devolver `""`.

```js
assert.isEmpty(repeatStringNumTimes('abc', 0));
```

# --seed--

## --seed-contents--

```js
function repeatStringNumTimes(str, num) {
  return str;
}

repeatStringNumTimes('abc', 3);
```

# --solutions--

```js
function repeatStringNumTimes(str, num) {
  if (num < 1) return '';
  return num === 1 ? str : str + repeatStringNumTimes(str, num - 1);
}

repeatStringNumTimes('abc', 3);
```
