---
id: 56533eb9ac21ba0edf2244c2
title: Повернення значення функції за допомогою return
challengeType: 1
forumTopicId: 18271
dashedName: return-a-value-from-a-function-with-return
---

# --description--

We can pass values into a function with <dfn>arguments</dfn>. You can use a `return` statement to send a value back out of a function.

**Наприклад:**

```js
function plusThree(num) {
  return num + 3;
}

const answer = plusThree(5);
```

`answer` набуває значення `8`.

`plusThree` приймає <dfn>аргумент</dfn> для `num` і повертає значення, яке дорівнює `num + 3`.

# --instructions--

Створіть функцію `timesFive`, що приймає один аргумент, множить його на `5` і повертає нове значення.

# --hints--

`timesFive` повинна бути функцією

```js
assert(typeof timesFive === 'function');
```

`timesFive(5)` має повертати `25`

```js
assert(timesFive(5) === 25);
```

`timesFive(2)` має повертати `10`

```js
assert(timesFive(2) === 10);
```

`timesFive(0)` має повертати `0`

```js
assert(timesFive(0) === 0);
```

# --seed--

## --seed-contents--

```js

```

# --solutions--

```js
function timesFive(num) {
  return num * 5;
}
timesFive(10);
```
