---
id: 56533eb9ac21ba0edf2244ac
title: 数字递增
challengeType: 1
forumTopicId: 18201
dashedName: increment-a-number-with-javascript
---

# --description--

You can easily <dfn>increment</dfn> or add one to a variable with the `++` operator.

```js
i++;
```

等效于：

```js
i = i + 1;
```

**注意：**`i++;` 这种写法省去了书写等号的必要。

# --instructions--

修改代码，使用 `++` 来对变量 `myVar` 进行自增操作。

# --hints--

`myVar` 应该等于 `88`。

```js
assert(myVar === 88);
```

不应该使用赋值运算符。

```js
assert(
  /let\s+myVar\s*=\s*87;\s*\/*.*\s*([+]{2}\s*myVar|myVar\s*[+]{2})/.test(__helpers.removeJSComments(code))
);
```

应该使用 `++` 运算符。

```js
assert(/[+]{2}\s*myVar|myVar\s*[+]{2}/.test(__helpers.removeJSComments(code)));
```

不应该修改注释上面的代码。

```js
assert(/let myVar = 87;/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'myVar = ' + z;})(myVar);
```

## --seed-contents--

```js
let myVar = 87;

// Only change code below this line
myVar = myVar + 1;
```

# --solutions--

```js
let myVar = 87;
myVar++;
```
