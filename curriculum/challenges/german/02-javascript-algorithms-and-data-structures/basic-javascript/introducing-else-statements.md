---
id: 56533eb9ac21ba0edf2244da
title: Einführung in die Else-Anweisungen
challengeType: 1
forumTopicId: 18207
dashedName: introducing-else-statements
---

# --description--

When a condition for an `if` statement is true, the block of code following it is executed. What about when that condition is false? Normally nothing would happen. With an `else` statement, an alternate block of code can be executed.

```js
if (num > 10) {
  return "Bigger than 10";
} else {
  return "10 or Less";
}
```

# --instructions--

Kombiniere die `if`-Anweisungen zu einer einzigen `if/else`-Anweisung.

# --hints--

Du solltest nur eine `if`-Anweisung im Editor verwenden

```js
assert(__helpers.removeJSComments(code).match(/if/g).length === 1);
```

Du solltest eine `else`-Anweisung verwenden

```js
assert(/else/g.test(__helpers.removeJSComments(code)));
```

`testElse(4)` sollte den String `5 or Smaller` zurückgeben

```js
assert(testElse(4) === '5 or Smaller');
```

`testElse(5)` sollte den String `5 or Smaller` zurückgeben

```js
assert(testElse(5) === '5 or Smaller');
```

`testElse(6)` sollte den String `Bigger than 5` zurückgeben

```js
assert(testElse(6) === 'Bigger than 5');
```

`testElse(10)`sollte den String `Bigger than 5` zurückgeben

```js
assert(testElse(10) === 'Bigger than 5');
```

Du solltest den Code nicht oberhalb oder unterhalb der angegebenen Kommentare ändern.

```js
assert(/let result = "";/.test(__helpers.removeJSComments(code)) && /return result;/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
function testElse(val) {
  let result = "";
  // Only change code below this line

  if (val > 5) {
    result = "Bigger than 5";
  }

  if (val <= 5) {
    result = "5 or Smaller";
  }

  // Only change code above this line
  return result;
}

testElse(4);
```

# --solutions--

```js
function testElse(val) {
  let result = "";
  if(val > 5) {
    result = "Bigger than 5";
  } else {
    result = "5 or Smaller";
  }
  return result;
}
```
