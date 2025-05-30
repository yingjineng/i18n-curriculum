---
id: bad87fee1348bd9aedf08801
title: Інформація щодо елементу paragraph
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/ceZ7DtN'
forumTopicId: 18202
dashedName: inform-with-the-paragraph-element
---

# --description--

The `p` element is the preferred element for paragraph text on websites. `p` is short for "paragraph".

Ось як ви можете створити елемент paragraph:

```html
<p>I'm a p tag!</p>
```

# --instructions--

Створіть елемент `p` під `h2` елементом, і введіть текст `Hello Paragraph`.

**Примітка:** як правило, усі HTML теги повинні писатись із малої літери, наприклад `<p></p>` не `<P></P>`.

# --hints--

Ваш код повинен містити правильний елемент `p`.

```js
assert.lengthOf(document.querySelectorAll('p'),1);
```

Ваш елемент `p` повинен містити текст `Hello Paragraph`.

```js
assert.match(document.querySelector('p').textContent,/hello(\s)+paragraph/gi);
```

Елемент `p` повинен мати кінцевий тег.

```js
assert.match(code,/<\/p>/g);
assert.strictEqual(code.match(/<\/p>/g).length,code.match(/<p/g).length);
```

# --seed--

## --seed-contents--

```html
<h1>Hello World</h1>
<h2>CatPhotoApp</h2>
```

# --solutions--

```html
<h1>Hello World</h1>
<h2>CatPhotoApp</h2>
<p>Hello Paragraph</p>
```
