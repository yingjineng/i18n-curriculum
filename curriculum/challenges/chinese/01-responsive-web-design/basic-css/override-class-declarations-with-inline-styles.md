---
id: bad87fee1348bd9aedf06756
title: 内联样式的优先级
challengeType: 0
videoUrl: 'https://scrimba.com/c/cGJDRha'
forumTopicId: 18252
dashedName: override-class-declarations-with-inline-styles
---

# --description--

So we've proven that id declarations override class declarations, regardless of where they are declared in your `style` element CSS.

其实还有其他方法可以覆盖 CSS 样式。 你还记得行内样式吗？

# --instructions--

使用行内样式尝试让 `h1` 的字体颜色变白。 记住，内联样式看起来是像这样：

```html
<h1 style="color: green;">
```

`h1` 元素应继续保留 `blue-text` 和 `pink-text` 这两个 class。

# --hints--

`h1` 元素应包含 `pink-text` class。

```js
assert.isTrue(document.querySelector('h1').classList.contains('pink-text'));
```

`h1` 元素应包含 `blue-text` class。

```js
assert.isTrue(document.querySelector('h1').classList.contains('blue-text'));
```

`h1` 的 id 属性值应为 `orange-text`。

```js
assert.strictEqual(document.querySelector('h1').getAttribute('id'), 'orange-text');
```

`h1` 元素应含有行内样式。

```js
assert.exists(document.querySelector('h1[style]'));
```

`h1` 元素的字体颜色应该为白色。

```js
const h1Element = document.querySelector('h1');
const color = window.getComputedStyle(h1Element)['color']; 
assert.strictEqual(color, 'rgb(255, 255, 255)');
```

# --seed--

## --seed-contents--

```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  #orange-text {
    color: orange;
  }
  .pink-text {
    color: pink;
  }
  .blue-text {
    color: blue;
  }
</style>
<h1 id="orange-text" class="pink-text blue-text">Hello World!</h1>
```

# --solutions--

```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  #orange-text {
    color: orange;
  }
  .pink-text {
    color: pink;
  }
  .blue-text {
    color: blue;
  }
</style>
<h1 id="orange-text" class="pink-text blue-text" style="color: white">Hello World!</h1>
```
