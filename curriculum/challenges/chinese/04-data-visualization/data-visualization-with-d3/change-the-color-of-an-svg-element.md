---
id: 587d7fa9367417b2b2512bd1
title: 更改 SVG 元素的颜色
challengeType: 6
forumTopicId: 301480
dashedName: change-the-color-of-an-svg-element
---

# --description--

The bars are in the right position, but they are all the same black color. SVG has a way to change the color of the bars.

在 SVG 中， `rect` 图形用 `fill` 属性着色。 它支持十六进制代码、颜色名称、rgb 值以及更复杂的选项，比如渐变和透明。

# --instructions--

添加 `attr()` 方法，将所有条形图的 `fill` 设置为海军蓝。

# --hints--

所有条形图的 `fill` 颜色都应该是 navy（海军蓝）。

```js
const rect = document.querySelector('rect');
assert.exists(rect); 
const fill = window.getComputedStyle(rect)['fill'];
assert.strictEqual(fill, 'rgb(0, 0, 128)');
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    const w = 500;
    const h = 100;

    const svg = d3
      .select('body')
      .append('svg')
      .attr('width', w)
      .attr('height', h);

    svg
      .selectAll('rect')
      .data(dataset)
      .enter()
      .append('rect')
      .attr('x', (d, i) => i * 30)
      .attr('y', (d, i) => h - 3 * d)
      .attr('width', 25)
      .attr('height', (d, i) => 3 * d);
    // Add your code below this line



    // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    const w = 500;
    const h = 100;

    const svg = d3
      .select('body')
      .append('svg')
      .attr('width', w)
      .attr('height', h);

    svg
      .selectAll('rect')
      .data(dataset)
      .enter()
      .append('rect')
      .attr('x', (d, i) => i * 30)
      .attr('y', (d, i) => h - 3 * d)
      .attr('width', 25)
      .attr('height', (d, i) => 3 * d)
      .attr('fill', 'navy');
  </script>
</body>
```
