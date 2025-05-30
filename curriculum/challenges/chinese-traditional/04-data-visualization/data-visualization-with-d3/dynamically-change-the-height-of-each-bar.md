---
id: 587d7fa9367417b2b2512bcf
title: 動態更改每個條形的高度
challengeType: 6
forumTopicId: 301486
dashedName: dynamically-change-the-height-of-each-bar
---

# --description--

The height of each bar can be set to the value of the data point in the array, similar to how the `x` value was set dynamically.

```js
selection.attr('property', (d, i) => {});
```

`d` 是數據點值，`i` 是數組中數據點的索引。

# --instructions--

改變 `height` 屬性的回調函數，讓它返回數據值乘以 3 的值。

**注意：** 記住，把所有數據點乘以相同的常數來對數據進行縮放（就像放大）， 這有利於看清例子中條形數值之間的差異。

# --hints--

第一個 `rect` 的 `height` 應爲 `36`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[0]?.getAttribute('height'),
  '36'
);
```

第二個 `rect` 的 `height` 應爲 `93`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[1]?.getAttribute('height'),
  '93'
);
```

第三個 `rect` 的 `height` 應爲 `66`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[2]?.getAttribute('height'),
  '66'
);
```

第四個 `rect` 的 `height` 應爲 `51`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[3]?.getAttribute('height'),
  '51'
);
```

第五個 `rect` 的 `height` 應爲 `75`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[4]?.getAttribute('height'),
  '75'
);
```

第六個 `rect` 的 `height` 應爲 `54`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[5]?.getAttribute('height'),
  '54'
);
```

第七個 `rect` 的 `height` 應爲 `87`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[6]?.getAttribute('height'),
  '87'
);
```

第八個 `rect` 的 `height` 應爲 `42`。

```js
assert.strictEqual(
  document.querySelectorAll('rect')[7]?.getAttribute('height'),
  '42'
);
```

第九個 `rect` 的 `height` 應爲 `27`。

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
