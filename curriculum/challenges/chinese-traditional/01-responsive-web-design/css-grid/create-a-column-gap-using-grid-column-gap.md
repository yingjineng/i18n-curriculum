---
id: 5a9036ee38fddaf9a66b5d35
title: 使用 grid-column-gap 創建多列之間的間距
challengeType: 0
videoUrl: 'https://scrimba.com/p/pByETK/cVZ8vfD'
forumTopicId: 301124
dashedName: create-a-column-gap-using-grid-column-gap
---

# --description--

So far in the grids you have created, the columns have all been tight up against each other. Sometimes you want a gap in between the columns. To add a gap between the columns, use the `grid-column-gap` property like this:

```css
grid-column-gap: 10px;
```

這會爲我們創建的所有列之間都添加 10px 的空白間距。

# --instructions--

請爲網格中的所有列添加寬度爲 `20px` 的間距。

# --hints--

class 爲 `container` 的元素應具有 `grid-column-gap` 屬性且屬性值應爲 `20px`。

```js
assert.match(
  code,
  /.container\s*?{[\s\S]*grid-column-gap\s*?:\s*?20px\s*?;[\s\S]*}/gi
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
    grid-column-gap: 20px;
  }
</style>
```
