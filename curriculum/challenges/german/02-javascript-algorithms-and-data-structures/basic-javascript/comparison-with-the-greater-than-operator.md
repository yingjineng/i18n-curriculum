---
id: 56533eb9ac21ba0edf2244d4
title: Vergleich mit dem Größer-als-Operator
challengeType: 1
forumTopicId: 16786
dashedName: comparison-with-the-greater-than-operator
---

# --description--

The greater than operator (`>`) compares the values of two numbers. If the number to the left is greater than the number to the right, it returns `true`. Otherwise, it returns `false`.

Wie der Gleichheitsoperator konvertiert auch der Größer-als-Operator die Datentypen der Werte beim Vergleich.

**Beispiele**

```js
5   >  3  // true
7   > '3' // true
2   >  3  // false
'1' >  9  // false
```

# --instructions--

Füge den Größer-als-Operator zu den angegebenen Zeilen hinzu, damit die Rückgabeanweisungen einen Sinn ergeben.

# --hints--

`testGreaterThan(0)`sollte den String `10 or Under` zurückgeben

```js
assert(testGreaterThan(0) === '10 or Under');
```

`testGreaterThan(10)` sollte den String `10 or Under` zurückgeben

```js
assert(testGreaterThan(10) === '10 or Under');
```

`testGreaterThan(11)` sollte den String `Over 10` zurückgeben

```js
assert(testGreaterThan(11) === 'Over 10');
```

`testGreaterThan(99)` sollte den String `Over 10` zurückgeben

```js
assert(testGreaterThan(99) === 'Over 10');
```

`testGreaterThan(100)` sollte den String `Over 10` zurückgeben

```js
assert(testGreaterThan(100) === 'Over 10');
```

`testGreaterThan(101)` sollte den String `Over 100` zurückgeben

```js
assert(testGreaterThan(101) === 'Over 100');
```

`testGreaterThan(150)` sollte den String `Over 100` zurückgeben

```js
assert(testGreaterThan(150) === 'Over 100');
```

Du solltest den Operator `>` mindestens zweimal verwenden

```js
assert(__helpers.removeJSComments(code).match(/val\s*>\s*('|")*\d+('|")*/g).length > 1);
```

# --seed--

## --seed-contents--

```js
function testGreaterThan(val) {
  if (val) {  // Change this line
    return "Over 100";
  }

  if (val) {  // Change this line
    return "Over 10";
  }

  return "10 or Under";
}

testGreaterThan(10);
```

# --solutions--

```js
function testGreaterThan(val) {
  if (val > 100) {  // Change this line
    return "Over 100";
  }
  if (val > 10) {  // Change this line
    return "Over 10";
  }
  return "10 or Under";
}
```
