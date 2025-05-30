---
id: 587d7faa367417b2b2512bd6
title: 给 D3 元素添加工具提示
challengeType: 6
forumTopicId: 301470
dashedName: add-a-tooltip-to-a-d3-element
---

# --description--

A tooltip shows more information about an item on a page when the user hovers over that item. There are several ways to add a tooltip to a visualization. This challenge uses the SVG `title` element.

`title` 和 `text()` 方法一起给每组动态添加数据。

# --instructions--

在每个 `rect` 节点下附加 `title` 元素。 然后用回调函数调用 `text()` 方法使它的文本显示数据值。

# --hints--

你应该有 9 个 `title` 元素。

```js
assert.lengthOf(document.querySelectorAll('title'), 9);
```

第一个 `title` 元素的提示框文本应为 `12`。

```js
assert.strictEqual(document.querySelectorAll('title')[0]?.textContent, '12');
```

第二个 `title` 元素的提示框文本应为 `31`。

```js
assert.strictEqual(document.querySelectorAll('title')[1]?.textContent, '31');
```

第三个 `title` 元素的提示框文本应为 `22`。

```js
assert.strictEqual(document.querySelectorAll('title')[2]?.textContent, '22');
```

第四个 `title` 元素的提示框文本应为 `17`。

```js
assert.strictEqual(document.querySelectorAll('title')[3]?.textContent, '17');
```

第五个 `title` 元素的提示框文本应为 `25`。

```js
assert.strictEqual(document.querySelectorAll('title')[4]?.textContent, '25');
```

第六个 `title` 元素的提示框文本应为 `18`。

```js
assert.strictEqual(document.querySelectorAll('title')[5]?.textContent, '18');
```

第七个 `title` 元素的提示框文本应为 `29`。

```js
assert.strictEqual(document.querySelectorAll('title')[6]?.textContent, '29');
```

第八个 `title` 元素的提示框文本应为 `14`。

```js
assert.strictEqual(document.querySelectorAll('title')[7]?.textContent, '14');
```

第九个 `title` 元素的提示框文本应为 `9`。

```js
assert.strictEqual(document.querySelectorAll('title')[8]?.textContent, '9');
```

# --seed--

## --seed-contents--

```html
<style>
  .bar:hover {
    fill: brown;
  }
</style>
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
      .attr('height', (d, i) => d * 3)
      .attr('fill', 'navy')
      .attr('class', 'bar');
    // Add your code below this line



    // Add your code above this line

    svg
      .selectAll('text')
      .data(dataset)
      .enter()
      .append('text')
      .text(d => d)
      .attr('x', (d, i) => i * 30)
      .attr('y', (d, i) => h - (d * 3 + 3));
  </script>
</body>
```

# --solutions--

```html
<style>
  .bar:hover {
    fill: brown;
  }
</style>
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
      .attr('height', (d, i) => d * 3)
      .attr('fill', 'navy')
      .attr('class', 'bar')
      .append('title')
      .text(d => d);

    svg
      .selectAll('text')
      .data(dataset)
      .enter()
      .append('text')
      .text(d => d)
      .attr('x', (d, i) => i * 30)
      .attr('y', (d, i) => h - (d * 3 + 3));
  </script>
</body>
```
