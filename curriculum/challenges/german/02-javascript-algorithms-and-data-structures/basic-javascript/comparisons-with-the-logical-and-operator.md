---
id: 56533eb9ac21ba0edf2244d8
title: Vergleiche mit dem logischen Und-Operator
challengeType: 1
forumTopicId: 16799
dashedName: comparisons-with-the-logical-and-operator
---

# --description--

Sometimes you will need to test more than one thing at a time. The <dfn>logical and</dfn> operator (`&&`) returns `true` if and only if the <dfn>operands</dfn> to the left and right of it are true.

Den gleichen Effekt kannst du erzielen, indem du eine `if`-Anweisung in eine andere `if`-Anweisung verschachtelst.

```js
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
```

Dieser Code gibt `Yes` zurück, wenn `num` größer als `5` und kleiner als `10` ist. Die gleiche Logik kann mit dem Operator <dfn>logical and</dfn> geschrieben werden.

```js
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
```

# --instructions--

Ersetze die beiden if-Anweisungen durch eine Anweisung mit dem `&&`-Operator, die den String `Yes` zurückgibt, wenn `val` kleiner als oder gleich `50` und größer als oder gleich `25` ist. Andernfalls wird der String `No` zurückgegeben.

# --hints--

Du solltest den `&&`-Operator einmal verwenden

```js
assert(__helpers.removeJSComments(code).match(/&&/g).length === 1);
```

Du solltest nur eine `if`-Anweisung verwenden

```js
assert(__helpers.removeJSComments(code).match(/if/g).length === 1);
```

`testLogicalAnd(0)` sollte den String `No` zurückgeben

```js
assert(testLogicalAnd(0) === 'No');
```

`testLogicalAnd(24)` sollte den String `No` zurückgeben

```js
assert(testLogicalAnd(24) === 'No');
```

`testLogicalAnd(25)` sollte den String `Yes` zurückgeben

```js
assert(testLogicalAnd(25) === 'Yes');
```

`testLogicalAnd(30)` sollte den String `Yes` zurückgeben

```js
assert(testLogicalAnd(30) === 'Yes');
```

`testLogicalAnd(50)` sollte den String `Yes` zurückgeben

```js
assert(testLogicalAnd(50) === 'Yes');
```

`testLogicalAnd(51)` sollte den String `No` zurückgeben

```js
assert(testLogicalAnd(51) === 'No');
```

`testLogicalAnd(75)` sollte den String `No` zurückgeben

```js
assert(testLogicalAnd(75) === 'No');
```

`testLogicalAnd(80)` sollte den String `No` zurückgeben

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
