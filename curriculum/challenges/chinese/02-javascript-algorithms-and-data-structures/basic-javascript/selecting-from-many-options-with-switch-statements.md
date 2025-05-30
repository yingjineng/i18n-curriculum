---
id: 56533eb9ac21ba0edf2244dd
title: 使用 Switch 语句从许多选项中进行选择
challengeType: 1
forumTopicId: 18277
dashedName: selecting-from-many-options-with-switch-statements
---

# --description--

If you need to match one value against many options, you can use a <dfn>switch</dfn> statement. A `switch` statement compares the value to the <dfn>case</dfn> statements which define various possible values. Any valid JavaScript statements can be executed inside a <dfn>case</dfn> block and will run from the first matched `case` value until a `break` is encountered.

这是 `switch` 语句的示例：

```js
switch (fruit) {
  case "apple":
    console.log("The fruit is an apple");
    break;
  case "orange":
    console.log("The fruit is an orange");
    break;
}
```

测试 `case` 值使用严格相等（`===`）运算符进行比较。 `break` 告诉 JavaScript 停止执行 switch 语句。 如果遗漏了 `break` ，下一个语句将会被执行。

# --instructions--

写一个测试 `val` 的 switch 语句，并且根据下面的条件来设置不同的 `answer`：  
`1` - `alpha`  
`2` - `beta`  
`3` - `gamma`  
`4` - `delta`

# --hints--

`caseInSwitch(1)` 值应该为字符串 `alpha`

```js
assert(caseInSwitch(1) === 'alpha');
```

`caseInSwitch(2)` 值应该为字符串 `beta`

```js
assert(caseInSwitch(2) === 'beta');
```

`caseInSwitch(3)` 值应该为字符串 `gamma`

```js
assert(caseInSwitch(3) === 'gamma');
```

`caseInSwitch(4)` 值应该为字符串 `delta`

```js
assert(caseInSwitch(4) === 'delta');
```

不能使用任何 `if` 或 `else` 表达式

```js
assert(!/else/g.test(__helpers.removeJSComments(code)) || !/if/g.test(__helpers.removeJSComments(code)));
```

你应该有至少 3 个 `break` 表达式

```js
assert(__helpers.removeJSComments(code).match(/break/g).length > 2);
```

# --seed--

## --seed-contents--

```js
function caseInSwitch(val) {
  let answer = "";
  // Only change code below this line



  // Only change code above this line
  return answer;
}

caseInSwitch(1);
```

# --solutions--

```js
function caseInSwitch(val) {
  let answer = "";

  switch (val) {
    case 1:
      answer = "alpha";
      break;
    case 2:
      answer = "beta";
      break;
    case 3:
      answer = "gamma";
      break;
    case 4:
      answer = "delta";
  }
  return answer;
}
```
