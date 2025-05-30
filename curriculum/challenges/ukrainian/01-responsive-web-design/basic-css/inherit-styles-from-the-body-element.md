---
id: bad87fee1348bd9aedf08746
title: Успадкування стилів від елемента body
challengeType: 0
videoUrl: 'https://scrimba.com/c/c9bmdtR'
forumTopicId: 18204
dashedName: inherit-styles-from-the-body-element
---

# --description--

Now we've proven that every HTML page has a `body` element, and that its `body` element can also be styled with CSS.

Пам'ятайте, що ви можете оформляти елемент `body` як і будь-який інший елемент HTML і всі наступні елементи успадкують стилі `body`.

# --instructions--

First, create an `h1` element with the text `Hello World`.

Тепер, давайте задамо всім елементам на сторінці колір `green`, додавши `color: green;` до об'яви стилю елемента `body`.

Нарешті, задайте елементу `body` шрифт `monospace`, додавши `font-family: monospace;` до об'яви стилю елемента `body`.

# --hints--

Ви повинні створити елемент `h1`.

```js
assert.isNotEmpty(document.querySelectorAll('h1'));
```

Елемент `h1` повинен мати текст `Hello World`.

```js
assert.match(
  document.querySelector('h1').textContent,
  /hello world/i
);
```

Елемент `h1` повинен мати кінцевий тег.

```js
const commentlessCode = __helpers.removeHtmlComments(code);
assert.match(commentlessCode, /<\/h1>/g);
assert.match(commentlessCode, /<h1/g);
assert.lengthOf(commentlessCode.match(/<\/h1>/g), commentlessCode.match(/<h1/g).length);
```

Елемент `body` повинен мати властивість `color` зі значенням `green`.

```js
const bodyElement = document.querySelector('body');
const color = window.getComputedStyle(bodyElement)['color']; 
assert.strictEqual(color, 'rgb(0, 128, 0)');
```

Елемент `body` повинен мати властивість `font-family` зі значенням `monospace`.

```js
const bodyElement = document.querySelector('body');
const fontFamily = window.getComputedStyle(bodyElement)['font-family'];
assert.include(fontFamily.toLowerCase(), "monospace");
```

Елемент `h1` повинен успадкувати шрифт `monospace` від елемента `body`.

```js
const h1Element = document.querySelector('h1');
const fontFamily = window.getComputedStyle(h1Element)['font-family'];
assert.include(fontFamily.toLowerCase(), "monospace");
```

Елемент `h1` повинен успадкувати колір `green` від елементу `body`.

```js
const h1Element = document.querySelector('h1');
const color = window.getComputedStyle(h1Element)['color'];
assert.strictEqual(color, 'rgb(0, 128, 0)');
```

# --seed--

## --seed-contents--

```html
<style>
  body {
    background-color: black;
  }

</style>
```

# --solutions--

```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }

</style>
<h1>Hello World!</h1>
```
