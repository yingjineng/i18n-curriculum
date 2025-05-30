---
id: 587d7fa9367417b2b2512bcf
title: 动态更改每个条形的高度
challengeType: 6
forumTopicId: 301486
dashedName: dynamically-change-the-height-of-each-bar
---

# --description--

The height of each bar can be set to the value of the data point in the array, similar to how the `x` value was set dynamically.

```js
selection.attr('property', (d, i) => {});
```

`d` 是数据点值，`i` 是数组中数据点的索引。

# --instructions--

改变 `height` 属性的回调函数，让它返回数据值乘以 3 的值。

**注意：** 记住，把所有数据点乘以相同的常数来对数据进行缩放（就像放大）， 这有利于看清例子中条形数值之间的差异。

# --hints--

第一个 `rect` 的 `height` 应为 `36`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[0]?.getAttribute('height'),
  '36'
);
```

第二个 `rect` 的 `height` 应为 `93`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[1]?.getAttribute('height'),
  '93'
);
```

第三个 `rect` 的 `height` 应为 `66`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[2]?.getAttribute('height'),
  '66'
);
```

第四个 `rect` 的 `height` 应为 `51`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[3]?.getAttribute('height'),
  '51'
);
```

第五个 `rect` 的 `height` 应为 `75`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[4]?.getAttribute('height'),
  '75'
);
```

第六个 `rect` 的 `height` 应为 `54`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[5]?.getAttribute('height'),
  '54'
);
```

第七个 `rect` 的 `height` 应为 `87`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[6]?.getAttribute('height'),
  '87'
);
```

第八个 `rect` 的 `height` 应为 `42`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[7]?.getAttribute('height'),
  '42'
);
```

第九个 `rect` 的 `height` 应为 `27`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[8]?.getAttribute('height'),
  '27'
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
      .attr('y', 0)
      .attr('width', 25)
      .attr('height', (d, i) => {
        // Add your code below this line




        // Add your code above this line
      });
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
      .attr('y', 0)
      .attr('width', 25)
      .attr('height', (d, i) => {
        return d * 3;
      });
  </script>
</body>
```
