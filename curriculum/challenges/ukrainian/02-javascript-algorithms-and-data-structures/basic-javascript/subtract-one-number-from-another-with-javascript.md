---
id: cf1111c1c11feddfaeb4bdef
title: Віднімання одного числа від іншого з JavaScript
challengeType: 1
forumTopicId: 18314
dashedName: subtract-one-number-from-another-with-javascript
---

# --description--

We can also subtract one number from another.

JavaScript використовує символ `-` для віднімання.

**Приклад**

```js
const myVar = 12 - 6;
```

`myVar` тепер матиме значення `6`.
# --instructions--

Змініть `0` так, щоб різниця дорівнювала `12`.

# --hints--

Змінна `difference` повинна дорівнювати `12`.

```js
assert(difference === 12);
```

Ви повинні відняти лише одне число від `45`.

```js
assert(/difference=45-33;?/.test(__helpers.removeWhiteSpace(__helpers.removeJSComments(code))));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'difference = '+z;})(difference);
```

## --seed-contents--

```js
const difference = 45 - 0;
```

# --solutions--

```js
const difference = 45 - 33;
```
