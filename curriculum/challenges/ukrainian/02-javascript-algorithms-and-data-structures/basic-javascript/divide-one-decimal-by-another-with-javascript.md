---
id: bd7993c9ca9feddfaeb7bdef
title: Ділення одного десяткового числа на інше з JavaScript
challengeType: 1
forumTopicId: 18255
dashedName: divide-one-decimal-by-another-with-javascript
---

# --description--

Now let's divide one decimal by another.

# --instructions--

Змініть `0.0` таким чином, щоб частка (`quotient`) дорівнювала `2.2`.

# --hints--

Змінна `quotient` (частка) повинна дорівнювати `2.2`

```js
assert(quotient === 2.2);
```

Ви повинні використати оператор `/`, щоб поділити 4.4 на 2

```js
assert(/4\.40*\s*\/\s*2\.*0*/.test(__helpers.removeJSComments(code)));
```

Змінна-частка повинна бути присвоєна лише раз

```js
assert(__helpers.removeJSComments(code).match(/quotient\s*=/g).length === 1);
```

# --seed--

## --seed-contents--

```js
const quotient = 0.0 / 2.0; // Change this line
```

# --solutions--

```js
const quotient = 4.4 / 2.0;
```
