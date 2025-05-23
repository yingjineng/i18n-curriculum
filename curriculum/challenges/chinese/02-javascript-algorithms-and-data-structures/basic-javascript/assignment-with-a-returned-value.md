---
id: 56533eb9ac21ba0edf2244c3
title: 使用返回值赋值
challengeType: 1
forumTopicId: 16658
dashedName: assignment-with-a-returned-value
---

# --description--

If you'll recall from our discussion about <a href="/learn/javascript-algorithms-and-data-structures/basic-javascript/storing-values-with-the-assignment-operator" target="_blank" rel="noopener noreferrer nofollow">Storing Values with the Assignment Operator</a>, everything to the right of the equal sign is resolved before the value is assigned. This means we can take the return value of a function and assign it to a variable.

假设我们有一个预先定义的函数 `sum` ，它将两个数相加。

```js
ourSum = sum(5, 12);
```

调用 `sum` 函数，参数为 `5` 和 `12`，生成的返回值为 `17`。 将返回值赋给 `ourSum` 变量。

# --instructions--

调用 `processArg` 函数，参数为 `7`，然后把返回的值赋值给变量 `processed`。

# --hints--

`processed` 的值应为 `2`。

```js
assert(processed === 2);
```

应该将 `processArg` 赋值给 `processed`。

```js
assert(/processed\s*=\s*processArg\(\s*7\s*\)/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(){return "processed = " + processed})();
```

## --seed-contents--

```js
// Setup
let processed = 0;

function processArg(num) {
  return (num + 3) / 5;
}

// Only change code below this line

```

# --solutions--

```js
var processed = 0;

function processArg(num) {
  return (num + 3) / 5;
}

processed = processArg(7);
```
