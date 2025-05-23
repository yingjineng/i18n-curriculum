---
id: 56bbb991ad1ed5201cd392cf
title: 用函數編寫可重用代碼
challengeType: 1
forumTopicId: 18378
dashedName: write-reusable-javascript-with-functions
---

# --description--

In JavaScript, we can divide up our code into reusable parts called <dfn>functions</dfn>.

舉個例子：

```js
function functionName() {
  console.log("Hello World");
}
```

你可以通過函數名加上後面的小括號來調用（<dfn>invoke</dfn>）這個函數，就像這樣： `functionName();` 每次調用函數時，它都會在控制檯上打印消息 `Hello World`。 每次調用函數時，大括號之間的所有代碼都將被執行。

# --instructions--

<ol>
  <li>
    Create a function called <code>reusableFunction</code> which prints the string <code>Hi World</code> to the dev console.
  </li>
  <li>
    然後調用這個函數。
  </li>
</ol>

# --hints--

`reusableFunction` 應該是一個函數。

```js
assert(typeof reusableFunction === 'function');
```

如果調用 `reusableFunction`，應該在控制檯輸出字符串 `Hi World`。

```js
assert(testConsole());
```

在定義 `reusableFunction` 之後，就應該調用它。

```js
const functionStr = reusableFunction && __helpers.removeWhiteSpace(reusableFunction.toString());
const codeWithoutFunction = __helpers.removeWhiteSpace(__helpers.removeJSComments(code)).replace(/reusableFunction\(\)\{/g, '');
assert(/reusableFunction\(\)/.test(codeWithoutFunction));
```

# --seed--

## --after-user-code--

```js

function testConsole() {
  var logOutput = "";
  var originalConsole = console;
  var nativeLog = console.log;
  var hiWorldWasLogged = false;
  console.log = function (message) {
    if(message === 'Hi World')  {
      console.warn(message)
      hiWorldWasLogged = true;
    }
    if(message && message.trim) logOutput = message.trim();
    if(nativeLog.apply) {
      nativeLog.apply(originalConsole, arguments);
    } else {
      var nativeMsg = Array.prototype.slice.apply(arguments).join(' ');
      nativeLog(nativeMsg);
    }
  };
  reusableFunction();
  console.log = nativeLog;
  return hiWorldWasLogged;
}

```

## --seed-contents--

```js

```

# --solutions--

```js
function reusableFunction() {
  console.log("Hi World");
}
reusableFunction();
```
