---
id: 56533eb9ac21ba0edf2244b1
title: 复合赋值之 *=
challengeType: 1
forumTopicId: 16662
dashedName: compound-assignment-with-augmented-multiplication
---

# --description--

The `*=` operator multiplies a variable by a number.

```js
myVar = myVar * 5;
```

将 `myVar` 乘以 `5`。 等价于：

```js
myVar *= 5;
```

# --instructions--

使用 `*=` 操作符对 `a`、`b` 和 `c` 实现赋值相乘操作。

# --hints--

`a` 应该等于`25`。

```js
assert(a === 25);
```

`b` 应该等于`36`。

```js
assert(b === 36);
```

`c` 应该等于`46`。

```js
assert(c === 46);
```

应该对每个变量使用 `*=` 操作符。

```js
assert(__helpers.removeJSComments(code).match(/\*=/g).length === 3);
```

不要修改注释上面的代码。

```js
assert(
  /let a = 5;/.test(__helpers.removeJSComments(code)) &&
    /let b = 12;/.test(__helpers.removeJSComments(code)) &&
    /let c = 4\.6;/.test(__helpers.removeJSComments(code))
);
```

# --seed--

## --after-user-code--

```js
(function(a,b,c){ return "a = " + a + ", b = " + b + ", c = " + c; })(a,b,c);
```

## --seed-contents--

```js
let a = 5;
let b = 12;
let c = 4.6;

// Only change code below this line
a = a * 5;
b = 3 * b;
c = c * 10;
```

# --solutions--

```js
let a = 5;
let b = 12;
let c = 4.6;

a *= 5;
b *= 3;
c *= 10;
```
