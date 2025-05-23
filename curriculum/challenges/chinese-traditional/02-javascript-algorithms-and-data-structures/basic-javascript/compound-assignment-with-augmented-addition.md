---
id: 56533eb9ac21ba0edf2244af
title: 複合賦值之 +=
challengeType: 1
forumTopicId: 16661
dashedName: compound-assignment-with-augmented-addition
---

# --description--

In programming, it is common to use assignments to modify the contents of a variable. Remember that everything to the right of the equals sign is evaluated first, so we can say:

```js
myVar = myVar + 5;
```

給 `myVar` 加上 `5`。 這是最常見的運算賦值語句，即先運算、再賦值。還有一類操作符是一步到位，既做運算也賦值的。

其中一種就是 `+=` 運算符。

```js
let myVar = 1;
myVar += 5;
console.log(myVar);
```

控制檯將會顯示 `6`。

# --instructions--

使用 `+=` 操作符對 `a`、`b` 和 `c` 賦值。

# --hints--

`a` 應該等於 `15`。

```js
assert(a === 15);
```

`b` 應該等於 `26`。

```js
assert(b === 26);
```

`c` 應該等於 `19`。

```js
assert(c === 19);
```

應該對每個變量使用 `+=` 操作符。

```js
assert(__helpers.removeJSComments(code).match(/\+=/g).length === 3);
```

不要修改註釋上面的代碼。

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
