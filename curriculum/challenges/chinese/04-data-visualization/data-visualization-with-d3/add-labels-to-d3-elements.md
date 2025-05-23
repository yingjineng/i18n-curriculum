---
id: 587d7faa367417b2b2512bd2
title: 给 D3 元素添加标签
challengeType: 6
forumTopicId: 301476
dashedName: add-labels-to-d3-elements
---

# --description--

D3 lets you label a graph element, such as a bar, using the SVG `text` element.

和 `rect` 元素类似，`text` 元素也需要 `x` 和 `y` 属性来指定其放置在 SVG 上的位置， 它也需要能够获取数据来显示数据值。

D3 给了你很高的权限给图形添加标签。

# --instructions--

编辑器中的代码已经将数据绑定到每个新的 `text` 元素。 首先，在 `svg` 中添加 `text` 节点。 然后，添加 `x` 和 `y` 坐标属性， 它们的计算方法应该和 `rect` 中计算方法相同，除了 `text` 的 `y` 值应该使标签比条形图的高 3 个单位。 最后，用 D3 的 `text()` 方法将标签设置为和数据点相等的值。

**注意：** 对于标签比条形图高的情况，应决定 `text` 的 `y` 值应比条形图的 `y` 值大还是小 3 个单位。

# --hints--

第一个 `text` 元素应有一个值为 `12` 的标签，且 `y` 值为 `61`。

```js
assert.strictEqual(document.querySelectorAll('text')[0]?.textContent, '12');
assert.strictEqual(
  document.querySelectorAll('text')[0]?.getAttribute('y'),
  '61'
);
```

第二个 `text` 元素应有一个值为 `31` 的标签，且 `y` 值为 `4`。

```js
assert.strictEqual(document.querySelectorAll('text')[1]?.textContent, '31');
assert.strictEqual(
  document.querySelectorAll('text')[1]?.getAttribute('y'),
  '4'
);
```

第三个 `text` 元素应有一个值为 `22` 的标签，且 `y` 值为 `31`。

```js
assert.strictEqual(document.querySelectorAll('text')[2]?.textContent, '22');
assert.strictEqual(
  document.querySelectorAll('text')[2]?.getAttribute('y'),
  '31'
);
```

第四个 `text` 元素应有一个值为 `17` 的标签，且 `y` 值为 `46`。

```js
assert.strictEqual(document.querySelectorAll('text')[3]?.textContent, '17');
assert.strictEqual(
  document.querySelectorAll('text')[3]?.getAttribute('y'),
  '46'
);
```

第五个 `text` 元素应有一个值为 `25` 的标签，且 `y` 值为 `22`。

```js
assert.strictEqual(document.querySelectorAll('text')[4]?.textContent, '25');
assert.strictEqual(
  document.querySelectorAll('text')[4]?.getAttribute('y'),
  '22'
);
```

第六个 `text` 元素应有一个值为 `18` 的标签，且 `y` 值为 `43`。

```js
assert.strictEqual(document.querySelectorAll('text')[5]?.textContent, '18');
assert.strictEqual(
  document.querySelectorAll('text')[5]?.getAttribute('y'),
  '43'
);
```

第七个 `text` 元素应有一个值为 `29` 的标签，且 `y` 值为 `10`。

```js
assert.strictEqual(document.querySelectorAll('text')[6]?.textContent, '29');
assert.strictEqual(
  document.querySelectorAll('text')[6]?.getAttribute('y'),
  '10'
);
```

第八个 `text` 元素应有一个值为 `14` 的标签，其 `y` 值为 `55`。

```js
assert.strictEqual(document.querySelectorAll('text')[7]?.textContent, '14');
assert.strictEqual(
  document.querySelectorAll('text')[7]?.getAttribute('y'),
  '55'
);
```

第九个 `text` 元素应有一个值为 `9` 的标签，且 `y` 值为 `70`。

```js
assert.strictEqual(document.querySelectorAll('text')[8]?.textContent, '9');
assert.strictEqual(
  document.querySelectorAll('text')[8]?.getAttribute('y'),
  '70'
);
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
      .attr('height', (d, i) => 3 * d)
      .attr('fill', 'navy');

    svg.selectAll('text').data(dataset).enter();
    // Add your code below this line




    // Add your code above this line
  </script>
  <body></body>
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

    svg
      .selectAll('text')
      .data(dataset)
      .enter()
      .append('text')
      .attr('x', (d, i) => i * 30)
      .attr('y', (d, i) => h - 3 * d - 3)
      .text(d => d);
  </script>
  <body></body>
</body>
```
