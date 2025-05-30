---
id: 56533eb9ac21ba0edf2244c0
title: 函数中的全局作用域和局部作用域
challengeType: 1
forumTopicId: 18194
dashedName: global-vs--local-scope-in-functions
---

# --description--

It is possible to have both <dfn>local</dfn> and <dfn>global</dfn> variables with the same name. When you do this, the local variable takes precedence over the global variable.

下面为例：

```js
const someVar = "Hat";

function myFun() {
  const someVar = "Head";
  return someVar;
}
```

函数 `myFun` 将会返回字符串 `Head`，因为局部变量的优先级更高。

# --instructions--

给 `myOutfit` 添加一个局部变量来将 `outerWear` 的值重载为 `sweater`。

# --hints--

不要修改全局变量 `outerWear` 的值。

```js
assert(outerWear === 'T-Shirt');
```

`myOutfit` 应该返回 `sweater`。

```js
assert(myOutfit() === 'sweater');
```

不要修改 return 语句。

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
