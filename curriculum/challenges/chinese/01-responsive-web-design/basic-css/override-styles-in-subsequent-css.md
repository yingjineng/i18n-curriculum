---
id: bad87fee1348bd9aedf04756
title: Class 选择器的优先级高于继承样式
challengeType: 0
videoUrl: 'https://scrimba.com/c/cGJDQug'
forumTopicId: 18253
dashedName: override-styles-in-subsequent-css
---

# --description--

Our `pink-text` class overrode our `body` element's CSS declaration!

我们刚刚证明了 class 会覆盖 `body` 的 CSS 样式。 那么下一个问题是，要怎么样才能覆盖 `pink-text` class 中所定义的样式？

# --instructions--

创建一个 `blue-text` class，将元素的颜色设置为蓝色。 将它放在 `pink-text` class 下面。

将 `blue-text` class 应用于 `h1` 元素，看看它和该元素上的 `pink-text` class 哪一个会优先显示。

对一个 HTML 元素应用多个 class 属性时，它们之间可以用空格隔开，就像这样：

```html
class="class1 class2"
```

**注意：** HTML 元素里应用的 class 的先后顺序无关紧要。

但是，在 `<style>` 标签里面声明的 `class` 顺序十分重要，之后的声明会覆盖之前的声明。 第二个声明的优先级始终高于第一个声明。 由于 `.blue-text` 是在后面声明的，所以它的样式会覆盖 `.pink-text` 里的样式。

# --hints--

`h1` 元素应包含 `pink-text` class。

```js
assert.isTrue(document.querySelector('h1').classList.contains('pink-text'));
```

`h1` 元素应包含 `blue-text` class。

```js
assert.isTrue(document.querySelector('h1').classList.contains('blue-text'));
```

`blue-text` 和 `pink-text` 需同时应用于 `h1` 元素上。

```js
assert.isTrue(document.querySelector('.pink-text').classList.contains('blue-text'));
```

`h1` 元素的颜色应为蓝色。

```js
const h1Element = document.querySelector('h1');
const color = window.getComputedStyle(h1Element)['color']; 
assert.strictEqual(color, 'rgb(0, 0, 255)');
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
  .pink-text {
    color: pink;
  }
</style>
<h1 class="pink-text">Hello World!</h1>
```

# --solutions--

```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  .pink-text {
    color: pink;
  }

  .blue-text {
    color: blue;
  }  
</style>
<h1 class="pink-text blue-text">Hello World!</h1>
```
