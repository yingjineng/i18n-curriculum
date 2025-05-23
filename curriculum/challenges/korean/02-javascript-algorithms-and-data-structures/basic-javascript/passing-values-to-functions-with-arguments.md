---
id: 56533eb9ac21ba0edf2244bd
title: 인수를 사용해서 함수에 값을 전달하기
challengeType: 1
forumTopicId: 18254
dashedName: passing-values-to-functions-with-arguments
---

# --description--

<dfn>Parameters</dfn> are variables that act as placeholders for the values that are to be input to a function when it is called. When a function is defined, it is typically defined along with one or more parameters. The actual values that are input (or <dfn>"passed"</dfn>) into a function when it is called are known as <dfn>arguments</dfn>.

여기에 `param1` and `param2`이라는 2개의 파라미터를 가진 함수가 있습니다:

```js
function testFun(param1, param2) {
  console.log(param1, param2);
}
```

그리고 우리는 이 `testFun`를 다음과 같이 부를 수 있습니다: `testFun("Hello", "World");`. 우리는 여기서 `Hello`와 `World`라는 2개의 문자열 인수들을 전달합니다. 함수 내부에서 `param1`은 문자열 `Hello`와 같을 것이며 `param2`는 문자열 `World`와 같을 것입니다. 다른 인수들을 붙여서 다시 `testFun`를 부르는 것도 가능하며, 그 경우 파라미터들은 새로운 인수들의 값을 갖게 됩니다.

# --instructions--

<ol><li>Create a function called <code>functionWithArgs</code> that accepts two arguments and outputs their sum to the dev console.</li><li>2개의 수치를 받는 인수들을 가지는 함수를 부르세요.</li></ol>

# --hints--

`functionWithArgs`는 함수여야 합니다.

```js
assert(typeof functionWithArgs === 'function');
```

`functionWithArgs(1,2)`는 `3`을 출력해야 합니다.

```js
if (typeof functionWithArgs === 'function') {
  capture();
  functionWithArgs(1, 2);
  uncapture();
}
assert(logOutput == 3);
```

`functionWithArgs(7,9)`는 `16`을 출력해야 합니다.

```js
if (typeof functionWithArgs === 'function') {
  capture();
  functionWithArgs(7, 9);
  uncapture();
}
assert(logOutput == 16);
```

당신은 2개의 수치로 `functionWithArgs`를 정의한 후에 불러야 합니다.

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
