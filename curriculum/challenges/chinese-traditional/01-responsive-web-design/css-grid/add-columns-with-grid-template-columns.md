---
id: 5a9036d038fddaf9a66b5d32
title: 使用 grid-template-columns 添加多列
challengeType: 0
videoUrl: 'https://scrimba.com/p/pByETK/c7NzDHv'
forumTopicId: 301117
dashedName: add-columns-with-grid-template-columns
---

# --description--

Simply creating a grid element doesn't get you very far. You need to define the structure of the grid as well. To add some columns to the grid, use the `grid-template-columns` property on a grid container as demonstrated below:

```css
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```

上面的代碼會在網格容器中添加兩列，寬度均爲 50px。 `grid-template-columns` 屬性值的個數表示網格的列數，每個值表示相應的列寬度。

# --instructions--

請給網格容器設置三個列，每列寬度均爲 `100px`。

# --hints--

class 爲 `container` 的元素應具有 `grid-template-columns` 屬性，該屬性應有三個屬性值，均爲 `100px`。

```js
const templateColumns = new __helpers.CSSHelp(document).getStyle(
  '.container'
)?.gridTemplateColumns;
assert.strictEqual(templateColumns, '100px 100px 100px');
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
    display: grid;
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
    grid-template-columns: 100px 100px 100px;
  }
</style>
```
