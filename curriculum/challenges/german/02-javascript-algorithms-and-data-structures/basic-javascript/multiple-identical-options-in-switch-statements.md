---
id: 56533eb9ac21ba0edf2244df
title: Mehrere identische Optionen in switch-Anweisungen
challengeType: 1
forumTopicId: 18242
dashedName: multiple-identical-options-in-switch-statements
---

# --description--

If the `break` statement is omitted from a `switch` statement's `case`, the following `case` statement(s) are executed until a `break` is encountered. If you have multiple inputs with the same output, you can represent them in a `switch` statement like this:

```js
let result = "";
switch (val) {
  case 1:
  case 2:
  case 3:
    result = "1, 2, or 3";
    break;
  case 4:
    result = "4 alone";
}
```

Die Cases für 1, 2 und 3 führen alle zum gleichen Ergebnis.

# --instructions--

Schreibe eine switch-Anweisung, um `answer` für die folgenden Bereiche zu setzen:  
`1-3` - `Low`  
`4-6` - `Mid`  
`7-9` - `High`

**Hinweis:** Du brauchst eine `case`-Anweisung für jede Zahl im Bereich.

# --hints--

`sequentialSizes(1)` sollte den String `Low` zurückgeben

```js
assert(sequentialSizes(1) === 'Low');
```

`sequentialSizes(2)` sollte den String `Low` zurückgeben

```js
assert(sequentialSizes(2) === 'Low');
```

`sequentialSizes(3)` sollte den String `Low` zurückgeben

```js
assert(sequentialSizes(3) === 'Low');
```

`sequentialSizes(4)` sollte den String `Mid` zurückgeben

```js
assert(sequentialSizes(4) === 'Mid');
```

`sequentialSizes(5)` sollte den String `Mid` zurückgeben

```js
assert(sequentialSizes(5) === 'Mid');
```

`sequentialSizes(6)` sollte den String `Mid` zurückgeben

```js
assert(sequentialSizes(6) === 'Mid');
```

`sequentialSizes(7)` sollte den String `High` zurückgeben

```js
assert(sequentialSizes(7) === 'High');
```

`sequentialSizes(8)` sollte den String `High` zurückgeben

```js
assert(sequentialSizes(8) === 'High');
```

`sequentialSizes(9)` sollte den String `High` zurückgeben

```js
assert(sequentialSizes(9) === 'High');
```

Du solltest keine `if` oder `else`-Anweisungen verwenden

```js
assert(!/else/g.test(__helpers.removeJSComments(code)) || !/if/g.test(__helpers.removeJSComments(code)));
```

Du solltest neun `case`-Anweisungen verwenden

```js
assert(__helpers.removeJSComments(code).match(/case/g).length === 9);
```

# --seed--

## --seed-contents--

```js
function sequentialSizes(val) {
  let answer = "";
  // Only change code below this line



  // Only change code above this line
  return answer;
}

sequentialSizes(1);
```

# --solutions--

```js
function sequentialSizes(val) {
  let answer = "";

  switch (val) {
    case 1:
    case 2:
    case 3:
      answer = "Low";
      break;
    case 4:
    case 5:
    case 6:
      answer = "Mid";
      break;
    case 7:
    case 8:
    case 9:
      answer = "High";
  }

  return answer;
}
```
