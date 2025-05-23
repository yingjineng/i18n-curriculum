---
id: 587d7faa367417b2b2512bd6
title: D3 の要素にツールチップを追加する
challengeType: 6
forumTopicId: 301470
dashedName: add-a-tooltip-to-a-d3-element
---

# --description--

ツールチップは、ユーザーがアイテムにカーソルを合わせたときにそのアイテムに関する詳しい情報を表示します。 視覚化にツールチップを追加する方法はいくつかあります。 このチャレンジでは、SVG の `title` 要素を使用します。

`title` と `text()` メソッドを組み合わせて、バーにデータを動的に追加します。

# --instructions--

各 `rect` ノードの下に `title` 要素を追加してください。 次に、コールバック関数で `text()` メソッドを呼び出すことでデータ値をテキストで表示してください。

# --hints--

9 個の `title` 要素が必要です。

```js
assert.lengthOf(document.querySelectorAll('title'), 9);
```

最初の `title` 要素にはツールチップテキスト `12` が必要です。

```js
assert.strictEqual(document.querySelectorAll('title')[0]?.textContent, '12');
```

2 番目の `title` 要素にはツールチップテキスト `31` が必要です。

```js
assert.strictEqual(document.querySelectorAll('title')[1]?.textContent, '31');
```

3 番目の `title` 要素にはツールチップテキスト `22` が必要です。

```js
assert.strictEqual(document.querySelectorAll('title')[2]?.textContent, '22');
```

4 番目の `title` 要素にはツールチップテキスト `17` が必要です。

```js
assert.strictEqual(document.querySelectorAll('title')[3]?.textContent, '17');
```

5 番目の `title` 要素にはツールチップテキスト `25` が必要です。

```js
assert.strictEqual(document.querySelectorAll('title')[4]?.textContent, '25');
```

6 番目の `title` 要素にはツールチップテキスト `18` が必要です。

```js
assert.strictEqual(document.querySelectorAll('title')[5]?.textContent, '18');
```

7 番目の `title` 要素にはツールチップテキスト `29` が必要です。

```js
assert.strictEqual(document.querySelectorAll('title')[6]?.textContent, '29');
```

8 番目の `title` 要素にはツールチップテキスト `14` が必要です。

```js
assert.strictEqual(document.querySelectorAll('title')[7]?.textContent, '14');
```

9 番目の `title` 要素にはツールチップテキスト `9` が必要です。

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
