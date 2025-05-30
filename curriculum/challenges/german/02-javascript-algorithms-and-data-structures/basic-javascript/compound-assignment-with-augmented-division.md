---
id: 56533eb9ac21ba0edf2244b2
title: Kombination von Zuordnung und Division
challengeType: 1
forumTopicId: 16659
dashedName: compound-assignment-with-augmented-division
---

# --description--

The `/=` operator divides a variable by another number.

```js
myVar = myVar / 5;
```

Teilt `myVar` durch `5`. Dies kann wie folgt umgeschrieben werden:

```js
myVar /= 5;
```

# --instructions--

Ändere die Zuweisungen für `a`, `b` und `c` so, dass sie den Operator `/=` verwenden.

# --hints--

`a` sollte gleich `4` sein.

```js
assert(a === 4);
```

`b` sollte gleich `27` sein.

```js
assert(b === 27);
```

`c` sollte gleich `3` sein.

```js
assert(c === 3);
```

Du solltest für jede Variable den Operator `/=` verwenden.

```js
assert(__helpers.removeJSComments(code).match(/\/=/g).length === 3);
```

Du solltest den Code oberhalb des vorgegebenen Kommentars nicht verändern.

```js
assert(
  /let a = 48;/.test(__helpers.removeJSComments(code)) &&
    /let b = 108;/.test(__helpers.removeJSComments(code)) &&
    /let c = 33;/.test(__helpers.removeJSComments(code))
);
```

# --seed--

## --after-user-code--

```js
(function(a,b,c){ return "a = " + a + ", b = " + b + ", c = " + c; })(a,b,c);
```

## --seed-contents--

```js
let a = 48;
let b = 108;
let c = 33;

// Only change code below this line
a = a / 12;
b = b / 4;
c = c / 11;
```

# --solutions--

```js
let a = 48;
let b = 108;
let c = 33;

a /= 12;
b /= 4;
c /= 11;
```
