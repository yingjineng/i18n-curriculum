---
id: 56533eb9ac21ba0edf2244af
title: Kombination von Zuordnung und Addition
challengeType: 1
forumTopicId: 16661
dashedName: compound-assignment-with-augmented-addition
---

# --description--

In programming, it is common to use assignments to modify the contents of a variable. Remember that everything to the right of the equals sign is evaluated first, so we can say:

```js
myVar = myVar + 5;
```

um `5` zu `myVar` hinzuzufügen. Da dies ein so häufiges Muster ist, gibt es Operatoren, die sowohl eine mathematische Operation als auch eine Zuweisung in einem Schritt durchführen.

Ein solcher Operator ist der Operator `+=`.

```js
let myVar = 1;
myVar += 5;
console.log(myVar);
```

`6` würde in der Konsole angezeigt werden.

# --instructions--

Ändere die Zuweisungen für `a`, `b` und `c`, um den Operator `+=` zu verwenden.

# --hints--

`a` sollte gleich `15` sein.

```js
assert(a === 15);
```

`b` sollte gleich `26` sein.

```js
assert(b === 26);
```

`c` sollte gleich `19` sein.

```js
assert(c === 19);
```

Du solltest den Operator `+=` für jede Variable verwenden.

```js
assert(__helpers.removeJSComments(code).match(/\+=/g).length === 3);
```

Du solltest den Code oberhalb des vorgegebenen Kommentars nicht verändern.

```js
assert(
  /let a = 3;/.test(__helpers.removeJSComments(code)) &&
    /let b = 17;/.test(__helpers.removeJSComments(code)) &&
    /let c = 12;/.test(__helpers.removeJSComments(code))
);
```

# --seed--

## --after-user-code--

```js
(function(a,b,c){ return "a = " + a + ", b = " + b + ", c = " + c; })(a,b,c);
```

## --seed-contents--

```js
let a = 3;
let b = 17;
let c = 12;

// Only change code below this line
a = a + 12;
b = 9 + b;
c = c + 7;
```

# --solutions--

```js
let a = 3;
let b = 17;
let c = 12;

a += 12;
b += 9;
c += 7;
```
