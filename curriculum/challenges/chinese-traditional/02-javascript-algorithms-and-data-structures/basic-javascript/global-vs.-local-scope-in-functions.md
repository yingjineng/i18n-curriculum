---
id: 56533eb9ac21ba0edf2244c0
title: 函數中的全局作用域和局部作用域
challengeType: 1
forumTopicId: 18194
dashedName: global-vs--local-scope-in-functions
---

# --description--

It is possible to have both <dfn>local</dfn> and <dfn>global</dfn> variables with the same name. When you do this, the local variable takes precedence over the global variable.

下面爲例：

```js
const someVar = "Hat";

function myFun() {
  const someVar = "Head";
  return someVar;
}
```

函數 `myFun` 將會返回字符串 `Head`，因爲局部變量的優先級更高。

# --instructions--

給 `myOutfit` 添加一個局部變量來將 `outerWear` 的值重載爲 `sweater`。

# --hints--

不要修改全局變量 `outerWear` 的值。

```js
assert(outerWear === 'T-Shirt');
```

`myOutfit` 應該返回 `sweater`。

```js
assert(myOutfit() === 'sweater');
```

不要修改 return 語句。

```js
assert(/return outerWear/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line

  // Only change code above this line
  return outerWear;
}

myOutfit();
```

# --solutions--

```js
const outerWear = "T-Shirt";
function myOutfit() {
  const outerWear = "sweater";
  return outerWear;
}
```
