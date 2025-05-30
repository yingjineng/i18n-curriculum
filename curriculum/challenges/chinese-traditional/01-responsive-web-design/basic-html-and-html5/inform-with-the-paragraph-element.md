---
id: bad87fee1348bd9aedf08801
title: 用 p 元素代表段落
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/ceZ7DtN'
forumTopicId: 18202
dashedName: inform-with-the-paragraph-element
---

# --description--

The `p` element is the preferred element for paragraph text on websites. `p` is short for "paragraph".

你可以像這樣創建一個段落：

```html
<p>I'm a p tag!</p>
```

# --instructions--

在 `h2` 元素下方添加一個 `p` 元素，其內容是 `Hello Paragraph`。

**注意：** 按照慣例，所有 HTML 標籤都應該是小寫字母，例如應使用 `<p></p>`，而不會使用 `<P></P>`。

# --hints--

應包含一個 `p` 元素。

```js
assert.lengthOf(document.querySelectorAll('p'),1);
```

`p` 元素的內容文本應爲 `Hello Paragraph`。

```js
assert.match(document.querySelector('p').textContent,/hello(\s)+paragraph/gi);
```

`p` 元素應有結束標籤。

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
