---
id: 5a9036ee38fddaf9a66b5d37
title: 使用 grid-gap 为网格添加间距
challengeType: 0
videoUrl: 'https://scrimba.com/p/pByETK/ca2qVtv'
forumTopicId: 301118
dashedName: add-gaps-faster-with-grid-gap
---

# --description--

`grid-gap` is a shorthand property for `grid-row-gap` and `grid-column-gap` from the previous two challenges that's more convenient to use. If `grid-gap` has one value, it will create a gap between all rows and columns. However, if there are two values, it will use the first one to set the gap between the rows and the second value for the columns.

# --instructions--

请使用 `grid-gap` 属性设置行间距为 `10px`、列间距为 `20px`。

# --hints--

`container` class 应该有一个 `grid-gap` 属性，在行之间设置 `10px` 的间距，在列之间设置 `20px` 的间距。

```js
assert.match(
  code,
  /.container\s*?{[\s\S]*grid-gap\s*?:\s*?10px\s+?20px\s*?;[\s\S]*}/gi
);
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
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
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
    grid-gap: 10px 20px;
  }
</style>
```
