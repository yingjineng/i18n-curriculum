---
id: 596e457071c35c882915b3e4
title: Vergleiche eine Liste von Strings
challengeType: 1
forumTopicId: 302235
dashedName: compare-a-list-of-strings
---

# --description--

Eine Liste ist eine geordnete Menge von Werten, die Duplikate enthalten kann. Hier ist ein Beispiel:

```js
const list = [['AA',  'BB', 'CC'], ['AA', 'ACB', 'AA'], [], ['AA']];
````

Given a list of arbitrarily many strings, implement a function for each of the following conditions:

<ul>
  <li>test if they are all lexically equal</li>
  <li>test if every string is lexically less than the one after it  (i.e. whether the list is in strict ascending order)</li>
</ul>

# --hints--

`allEqual` should be a function.

```js
assert(typeof allEqual === 'function');
```

`azSorted` sollte eine Funktion sein.

```js
assert(typeof azSorted === 'function');
```

`allEqual(["AA", "AA", "AA", "AA"])` sollte true zurückgeben.

```js
assert(allEqual(testCases[0]));
```

`azSorted(["AA", "AA", "AA", "AA"])` sollte false zurückgeben.

```js
assert(!azSorted(testCases[0]));
```

`allEqual(["AA", "ACB", "BB", "CC"])` sollte false zurückgeben.

```js
assert(!allEqual(testCases[1]));
```

`azSorted(["AA", "ACB", "BB", "CC"])` sollte true zurückgeben.

```js
assert(azSorted(testCases[1]));
```

`allEqual([])` sollte true zurückgeben.

```js
assert(allEqual(testCases[2]));
```

`azSorted([])` sollte true zurückgeben.

```js
assert(azSorted(testCases[2]));
```

`allEqual(["AA"])` sollte true zurückgeben.

```js
assert(allEqual(testCases[3]));
```

`azSorted(["AA"])` sollte true zurückgeben.

```js
assert(azSorted(testCases[3]));
```

`allEqual(["BB", "AA"])` sollte false zurückgeben.

```js
assert(!allEqual(testCases[4]));
```

`azSorted(["BB", "AA"])` sollte false zurückgeben.

```js
assert(!azSorted(testCases[4]));
```

# --seed--

## --after-user-code--

```js
const testCases = [['AA', 'AA', 'AA', 'AA'], ['AA', 'ACB', 'BB', 'CC'], [], ['AA'], ['BB', 'AA']];
```

## --seed-contents--

```js
function allEqual(arr) {

  return true;
}

function azSorted(arr) {

  return true;
}
```

# --solutions--

```js
function allEqual(a) {
  let out = true;
  let i = 0;
  while (++i < a.length) {
    out = out && (a[i - 1] === a[i]);
  } return out;
}

function azSorted(a) {
  let out = true;
  let i = 0;
  while (++i < a.length) {
    out = out && (a[i - 1] < a[i]);
  } return out;
}
```
