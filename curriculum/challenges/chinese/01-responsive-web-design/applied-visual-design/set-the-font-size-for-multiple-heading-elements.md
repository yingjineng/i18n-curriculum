---
id: 587d781c367417b2b2512ac2
title: 设置多个标题元素的 font-size
challengeType: 0
videoUrl: 'https://scrimba.com/c/cPpQNT3'
forumTopicId: 301067
dashedName: set-the-font-size-for-multiple-heading-elements
---

# --description--

The `font-size` property is used to specify how large the text is in a given element. This rule can be used for multiple elements to create visual consistency of text on a page. In this challenge, you'll set the values for all `h1` through `h6` tags to balance the heading sizes.

# --instructions--

在 `style` 标签中, 对各元素的 `font-size` 进行如下设置：

- `h1` tag to 68px.
- 将 `h2` 标签的文字大小设为 52px。
- 将 `h3` 标签的文字大小设为 40px
- 将 `h4` 标签的文字大小设为 32px
- 将 `h5` 标签的文字大小设为 21px
- 将 `h6` 标签的文字大小设为 14px

# --hints--

`h1` 标签的 `font-size` 属性值应为 68px。

```js
 const fontSizeOfh1 = new __helpers.CSSHelp(document).getStyle('h1')?.getPropertyValue('font-size');
 assert.equal(fontSizeOfh1 ,'68px');
```

`h2` 标签的 `font-size` 属性值应为 52px。

```js
 const fontSizeOfh2 = new __helpers.CSSHelp(document).getStyle('h2')?.getPropertyValue('font-size');
 assert.equal(fontSizeOfh2 ,'52px');
```

`h3` 标签的 `font-size` 属性值应为 40px。

```js
 const fontSizeOfh3 = new __helpers.CSSHelp(document).getStyle('h3')?.getPropertyValue('font-size');
 assert.equal(fontSizeOfh3 ,'40px');
```

`h4` 标签的 `font-size` 属性值应为 32px。

```js
 const fontSizeOfh4 = new __helpers.CSSHelp(document).getStyle('h4')?.getPropertyValue('font-size');
 assert.equal(fontSizeOfh4 , '32px');
```

`h5` 标签的 `font-size` 属性值应为 21px。

```js
 const fontSizeOfh5 = new __helpers.CSSHelp(document).getStyle('h5')?.getPropertyValue('font-size');
 assert.equal(fontSizeOfh5 ,'21px');
```

`h6` 标签的 `font-size` 属性值应为 14px。

```js
 const fontSizeOfh6 = new __helpers.CSSHelp(document).getStyle('h6')?.getPropertyValue('font-size');
 assert.equal(fontSizeOfh6 , '14px');
```

# --seed--

## --seed-contents--

```html
<style>






</style>
<h1>This is h1 text</h1>
<h2>This is h2 text</h2>
<h3>This is h3 text</h3>
<h4>This is h4 text</h4>
<h5>This is h5 text</h5>
<h6>This is h6 text</h6>
```

# --solutions--

```html
<style>
  h1 {
    font-size: 68px;
  }
  h2 {
    font-size: 52px;
  }
  h3 {
    font-size: 40px;
  }
  h4 {
    font-size: 32px;
  }
  h5 {
    font-size: 21px;
  }
  h6 {
    font-size: 14px;
  }
</style>
<h1>This is h1 text</h1>
<h2>This is h2 text</h2>
<h3>This is h3 text</h3>
<h4>This is h4 text</h4>
<h5>This is h5 text</h5>
<h6>This is h6 text</h6>
```
