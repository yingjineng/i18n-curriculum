---
id: bd7993c9ca9feddfaeb7bdef
title: 兩個小數相除
challengeType: 1
forumTopicId: 18255
dashedName: divide-one-decimal-by-another-with-javascript
---

# --description--

Now let's divide one decimal by another.

# --instructions--

改變數值 `0.0` 的值讓變量 `quotient` 的值等於 `2.2`。

# --hints--

`quotient` 的值應該等於`2.2`。

```js
assert(quotient === 2.2);
```

使用 `/` 運算符將 4.4 除以 2。

```js
assert(/4\.40*\s*\/\s*2\.*0*/.test(__helpers.removeJSComments(code)));
```

quotient 變量應該只被賦值一次。

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
