---
id: cf1111c1c11feddfaeb6bdef
title: Ділення одного числа на інше з JavaScript
challengeType: 1
forumTopicId: 17566
dashedName: divide-one-number-by-another-with-javascript
---

# --description--

We can also divide one number by another.

JavaScript використовує символ `/` для ділення.

**Приклад**

```js
const myVar = 16 / 2;
```

Тепер `myVar` має значення `8`.
# --instructions--

Змініть `0` таким чином, щоб частка (`quotient`) дорівнювала `2`.

# --hints--

Змінна `quotient` (частка) повинна дорівнювати 2.

```js
assert(quotient === 2);
```

Ви повинні використати оператор `/`.

```js
assert(/\d+\s*\/\s*\d+/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'quotient = '+z;})(quotient);
```

## --seed-contents--

```js
const quotient = 66 / 0;
```

# --solutions--

```js
const quotient = 66 / 33;
```
