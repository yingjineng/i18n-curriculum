---
id: 5a858944d96184f06fd60d61
title: 創建你的第一個 CSS 網格
challengeType: 0
videoUrl: 'https://scrimba.com/p/pByETK/cqwREC4'
forumTopicId: 301129
dashedName: create-your-first-css-grid
---

# --description--

Turn any HTML element into a grid container by setting its `display` property to `grid`. This gives you the ability to use all the other properties associated with CSS Grid.

**注意：** 在 CSS 網格中，父元素稱爲<dfn>容器（container）</dfn>，它的子元素稱爲<dfn>項（items）</dfn>。

# --instructions--

請將 class 爲 `container` 的 div 的 display 屬性值設置爲 `grid`。

# --hints--

`container` class 應具有 `display` 屬性，屬性值應爲 `grid`。

```js
assert.match(code, /.container\s*?{[\s\S]*display\s*?:\s*?grid\s*?;[\s\S]*}/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  .d1 {
    background: LightSkyBlue;
  }
  .d2 {
    background: LightSalmon;
  }
  .d3 {
    background: PaleTurquoise;
  }
  .d4 {
    background: LightPink;
  }
  .d5 {
    background: PaleGreen;
  }

  .container {
    font-size: 40px;
    width: 100%;
    background: LightGray;
    /* Only change code below this line */


    /* Only change code above this line */
  }
</style>

<div class="container">
  <div class="d1">1</div>
  <div class="d2">2</div>
  <div class="d3">3</div>
  <div class="d4">4</div>
  <div class="d5">5</div>
</div>
```

# --solutions--

```html
<style>
  .container {
    display: grid;
  }
</style>
```
