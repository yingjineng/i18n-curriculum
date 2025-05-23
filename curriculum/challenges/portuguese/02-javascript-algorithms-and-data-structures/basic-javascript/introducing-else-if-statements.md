---
id: 56533eb9ac21ba0edf2244db
title: Introduzir instruções else if
challengeType: 1
forumTopicId: 18206
dashedName: introducing-else-if-statements
---

# --description--

If you have multiple conditions that need to be addressed, you can chain `if` statements together with `else if` statements.

```js
if (num > 15) {
  return "Bigger than 15";
} else if (num < 5) {
  return "Smaller than 5";
} else {
  return "Between 5 and 15";
}
```

# --instructions--

Converta a lógica para usar instruções `else if`.

# --hints--

Você deve ter pelo menos duas instruções `else`

```js
assert(__helpers.removeJSComments(code).match(/else/g).length > 1);
```

Você deve ter pelo menos duas instruções `if`

```js
assert(__helpers.removeJSComments(code).match(/if/g).length > 1);
```

Você deve ter chaves de abertura e fechamento para cada bloco de código de `if else`.

```js
assert(
  __helpers.removeJSComments(code).match(
    /if\s*\((.+)\)\s*\{[\s\S]+\}\s*else\s+if\s*\((.+)\)\s*\{[\s\S]+\}\s*else\s*\{[\s\S]+\s*\}/
  )
);
```

`testElseIf(0)` deve retornar a string `Smaller than 5`

```js
assert(testElseIf(0) === 'Smaller than 5');
```

`testElseIf(5)` deve retornar a string `Between 5 and 10`

```js
assert(testElseIf(5) === 'Between 5 and 10');
```

`testElseIf(7)` deve retornar a string `Between 5 and 10`

```js
assert(testElseIf(7) === 'Between 5 and 10');
```

`testElseIf(10)` deve retornar a string `Between 5 and 10`

```js
assert(testElseIf(10) === 'Between 5 and 10');
```

`testElseIf(12)` deve retornar a string `Greater than 10`

```js
assert(testElseIf(12) === 'Greater than 10');
```

# --seed--

## --seed-contents--

```js
function testElseIf(val) {
  if (val > 10) {
    return "Greater than 10";
  }

  if (val < 5) {
    return "Smaller than 5";
  }

  return "Between 5 and 10";
}

testElseIf(7);
```

# --solutions--

```js
function testElseIf(val) {
  if(val > 10) {
    return "Greater than 10";
  } else if(val < 5) {
    return "Smaller than 5";
  } else {
    return "Between 5 and 10";
  }
}
```
