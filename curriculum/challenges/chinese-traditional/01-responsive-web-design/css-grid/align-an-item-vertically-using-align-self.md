---
id: 5a90375238fddaf9a66b5d3b
title: 使用 align-self 垂直對齊項目
challengeType: 0
videoUrl: 'https://scrimba.com/p/pByETK/cmzd4fz'
forumTopicId: 301123
dashedName: align-an-item-vertically-using-align-self
---

# --description--

Just as you can align an item horizontally, there's a way to align an item vertically as well. To do this, you use the `align-self` property on an item. This property accepts all of the same values as `justify-self` from the last challenge.

# --instructions--

請使用值 `end` 來讓 class 爲 `item3` 的網格項沿底端對齊。

# --hints--

class 爲 `item3` 的元素應具有 `align-self` 屬性且屬性值應爲 `end`。

```js
assert.match(code, /.item3\s*?{[\s\S]*align-self\s*?:\s*?end\s*?;[\s\S]*}/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  .item1 {
    background: LightSkyBlue;
  }
  .item2 {
    background: LightSalmon;
  }

  .item3 {
    background: PaleTurquoise;
    /* Only change code below this line */


    /* Only change code above this line */
  }

  .item4 {
    background: LightPink;
  }
  .item5 {
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
    grid-gap: 10px;
  }
</style>

<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
</div>
```

# --solutions--

```html
<style>
  .item3 {
    align-self: end;
  }
</style>
```
