---
id: 56533eb9ac21ba0edf2244bd
title: 將值傳遞給帶有參數的函數
challengeType: 1
forumTopicId: 18254
dashedName: passing-values-to-functions-with-arguments
---

# --description--

<dfn>Parameters</dfn> are variables that act as placeholders for the values that are to be input to a function when it is called. When a function is defined, it is typically defined along with one or more parameters. The actual values that are input (or <dfn>"passed"</dfn>) into a function when it is called are known as <dfn>arguments</dfn>.

這是帶有兩個參數的函數，`param1` 和 `param2`：

```js
function testFun(param1, param2) {
  console.log(param1, param2);
}
```

然後我們可以調用 `testFun`，就像這樣： `testFun("Hello", "World");`。 我們傳入了兩個字符串參數， `Hello` 和 `World`。 在函數中，`param1` 等於字符串 `Hello` 以及 `param2` 等於字符串 `World`。 請注意，`testFun` 函數可以多次調用，每次調用時傳遞的參數會決定參數的實際值。

# --instructions--

<ol><li>Create a function called <code>functionWithArgs</code> that accepts two arguments and outputs their sum to the dev console.</li><li>自己指定兩個數字作爲參數，運行函數 functionWithArgs。</li></ol>

# --hints--

`functionWithArgs` 應該是一個函數。

```js
assert(typeof functionWithArgs === 'function');
```

`functionWithArgs(1,2)` 應該輸出 `3`。

```js
if (typeof functionWithArgs === 'function') {
  capture();
  functionWithArgs(1, 2);
  uncapture();
}
assert(logOutput == 3);
```

`functionWithArgs(7,9)` 應該輸出 `16`。

```js
if (typeof functionWithArgs === 'function') {
  capture();
  functionWithArgs(7, 9);
  uncapture();
}
assert(logOutput == 16);
```

在定義 `functionWithArgs` 之後記得傳入兩個數字調用它。

```js
assert(
  /functionWithArgs\([-+]?\d*\.?\d*,[-+]?\d*\.?\d*\)/.test(
    __helpers.removeJSComments(code).replace(/\s/g, '')
  )
);
```

# --seed--

## --before-user-code--

```js
var logOutput = "";
var originalConsole = console
function capture() {
    var nativeLog = console.log;
    console.log = function (message) {
        if(message) logOutput = JSON.stringify(message).trim();
        if(nativeLog.apply) {
          nativeLog.apply(originalConsole, arguments);
        } else {
          var nativeMsg = Array.prototype.slice.apply(arguments).join(' ');
          nativeLog(nativeMsg);
        }
    };
}

function uncapture() {
  console.log = originalConsole.log;
}

capture();
```

## --after-user-code--

```js
uncapture();

if (typeof functionWithArgs !== "function") { 
  (function() { return "functionWithArgs is not defined"; })();
} else {
  (function() { return logOutput || "console.log never called"; })();
}
```

## --seed-contents--

```js

```

# --solutions--

```js
function functionWithArgs(a, b) {
  console.log(a + b);
}
functionWithArgs(10, 5);
```
