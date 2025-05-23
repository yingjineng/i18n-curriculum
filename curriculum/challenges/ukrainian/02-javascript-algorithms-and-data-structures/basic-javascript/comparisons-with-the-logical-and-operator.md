---
id: 56533eb9ac21ba0edf2244d8
title: Порівняння з логічним оператором and
challengeType: 1
forumTopicId: 16799
dashedName: comparisons-with-the-logical-and-operator
---

# --description--

Sometimes you will need to test more than one thing at a time. The <dfn>logical and</dfn> operator (`&&`) returns `true` if and only if the <dfn>operands</dfn> to the left and right of it are true.

Такого ж результату можна досягнути, вклавши одну інструкцію `if` в іншу `if`.

```js
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
```

Цей код поверне `Yes`, якщо `num` більше ніж `5` та менше ніж `10`. Таку саму логіку можна записати за допомогою <dfn>логічного оператора and</dfn>.

```js
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
```

# --instructions--

Замініть дві інструкції if на одну інструкцію, використавши оператор `&&`, який поверне рядок `Yes`, якщо `val` менше чи дорівнює `50` та більше чи дорівнює `25`. В іншому випадку поверніть рядок `No`.

# --hints--

Ви повинні використати оператор `&&` лише раз

```js
assert(__helpers.removeJSComments(code).match(/&&/g).length === 1);
```

Ви повинні мати лише одну інструкцію `if`

```js
assert(__helpers.removeJSComments(code).match(/if/g).length === 1);
```

`testLogicalAnd(0)` має повертати рядок `No`

```js
assert(testLogicalAnd(0) === 'No');
```

`testLogicalAnd(24)` має повертати рядок `No`

```js
assert(testLogicalAnd(24) === 'No');
```

`testLogicalAnd(25)` має повертати рядок `Yes`

```js
assert(testLogicalAnd(25) === 'Yes');
```

`testLogicalAnd(30)` має повертати рядок `Yes`

```js
assert(testLogicalAnd(30) === 'Yes');
```

`testLogicalAnd(50)` має повертати рядок `Yes`

```js
assert(testLogicalAnd(50) === 'Yes');
```

`testLogicalAnd(51)` має повертати рядок `No`

```js
assert(testLogicalAnd(51) === 'No');
```

`testLogicalAnd(75)` має повертати рядок `No`

```js
assert(testLogicalAnd(75) === 'No');
```

`testLogicalAnd(80)` має повертати рядок `No`

```js
assert(testLogicalAnd(80) === 'No');
```

# --seed--

## --seed-contents--

```js
function testLogicalAnd(val) {
  // Only change code below this line

  if (val) {
    if (val) {
      return "Yes";
    }
  }

  // Only change code above this line
  return "No";
}

testLogicalAnd(10);
```

# --solutions--

```js
function testLogicalAnd(val) {
  if (val >= 25 && val <= 50) {
    return "Yes";
  }
  return "No";
}
```
