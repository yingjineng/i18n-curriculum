---
id: cf1111c1c11feddfaeb3bdef
title: Додавання двох чисел з JavaScript
challengeType: 1
forumTopicId: 16650
dashedName: add-two-numbers-with-javascript
---

# --description--

`Number` is a data type in JavaScript which represents numeric data.

Тепер спробуємо додати два числа за допомогою JavaScript.

JavaScript використовує символ `+` як оператор додавання, якщо він розміщений між двома числами.

**Приклад:**

```js
const myVar = 5 + 10;
```

Тепер `myVar` має значення `15`.

# --instructions--

Змініть `0` так, щоб сума дорівнювала `20`.

# --hints--

`sum` має дорівнювати `20`.

```js
assert(sum === 20);
```

Ви повинні використати оператор `+`.

```js
assert(/\+/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'sum = '+z;})(sum);
```

## --seed-contents--

```js
const sum = 10 + 0;
```

# --solutions--

```js
const sum = 10 + 10;
```
