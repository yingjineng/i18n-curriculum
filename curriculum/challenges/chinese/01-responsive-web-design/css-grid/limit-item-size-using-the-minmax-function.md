---
id: 5a94fe4469fb03452672e460
title: 使用 minmax 函数限制项目大小
challengeType: 0
videoUrl: 'https://scrimba.com/p/pByETK/cD97RTv'
forumTopicId: 301131
dashedName: limit-item-size-using-the-minmax-function
---

# --description--

There's another built-in function to use with `grid-template-columns` and `grid-template-rows` called `minmax`. It's used to limit the size of items when the grid container changes size. To do this you need to specify the acceptable size range for your item. 以下是一个例子：

```css
grid-template-columns: 100px minmax(50px, 200px);
```

在上面的代码中，我们通过 `grid-template-columns` 添加了两列，第一列宽度为 100px，第二列宽度最小值是 50px，最大值是 200px。

# --instructions--

请用 `minmax` 函数替换 `repeat` 函数中的 `1fr`，限定其最小值为 `90px`，最大值为`1fr`。 你可以调整最右侧的预览面板查看效果。

# --hints--

class 为 `container` 的元素应使用 `grid-template-columns` 属性设置 3 列，其中，每列最小宽度应为 `90px`，最大宽度应为 `1fr`。

```js
assert.match(
  code,
  /.container\s*?{[\s\S]*grid-template-columns\s*?:\s*?repeat\s*?\(\s*?3\s*?,\s*?minmax\s*?\(\s*?90px\s*?,\s*?1fr\s*?\)\s*?\)\s*?;[\s\S]*}/gi
);
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
    /* Only change code below this line */

    grid-template-columns: repeat(3, 1fr);

    /* Only change code above this line */
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
  .container {
    grid-template-columns: repeat(3, minmax(90px, 1fr));
  }
</style>
```
