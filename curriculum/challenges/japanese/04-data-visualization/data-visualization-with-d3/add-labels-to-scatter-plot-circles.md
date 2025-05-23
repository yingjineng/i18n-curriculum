---
id: 587d7fab367417b2b2512bd9
title: 散布図の円にラベルを追加する
challengeType: 6
forumTopicId: 301477
dashedName: add-labels-to-scatter-plot-circles
---

# --description--

散布図の点のラベルを作成するために、テキストを追加することができます。

目標は、`dataset` 内の各アイテムの 1 つ目 (`x`) と 2 つ目 (`y`) のフィールドのカンマ区切り値を表示することです。

`text` ノードを SVG 上に配置するには `x` 属性と `y` 属性が必要です。 このチャレンジでは、(高さを決定する) `y` 値には、`circle` が `cy` 属性に対して使用するものと同じ値を使用できます。 `x` 値は、ラベルが見えるように、`circle` の `cx` 値よりも若干大きくすることができます。 これにより、プロットされた点の右側にラベルが移動します。

# --instructions--

`text` 要素を使用して、散布図上の各点にラベルを付けてください。 ラベルのテキストは、1 つのカンマと 1 つのスペースで区切られた 2 つの値にする必要があります。 たとえば、最初の点のラベルは `34, 78` です。 `circle` 上の `cx` 属性に使用した値よりも `5` 単位大きくなるように、`x` 属性を設定してください。 `y` 属性を、`circle` の `cy` 値に使用したのと同じ方法で設定してください。

# --hints--

10 個の `text` 要素が必要です。

```js
assert.lengthOf(document.querySelectorAll('text'), 10);
```

最初のラベルはテキストを `34, 78` 、`x` 値を`39`、そして `y` 値を `422` にする必要があります。

```js
const labelOne = document.querySelector('text');
assert.strictEqual(labelOne?.textContent, '34, 78');
assert.strictEqual(labelOne?.getAttribute('x'), '39');
assert.strictEqual(labelOne?.getAttribute('y'), '422');
```

2 番目のラベルはテキストを `109, 280` 、`x` 値を `114`、そして `y` 値を `220` にする必要があります。

```js
const labelTwo = document.querySelectorAll('text')[1];
assert.strictEqual(labelTwo?.textContent, '109, 280');
assert.strictEqual(labelTwo?.getAttribute('x'), '114');
assert.strictEqual(labelTwo?.getAttribute('y'), '220');
```

3 番目のラベルはテキストを `310, 120` 、`x` 値を `315`、そして `y` 値を `380` にする必要があります。

```js
const labelThree = document.querySelectorAll('text')[2];
assert.strictEqual(labelThree?.textContent, '310, 120');
assert.strictEqual(labelThree?.getAttribute('x'), '315');
assert.strictEqual(labelThree?.getAttribute('y'), '380');
```

4 番目のラベルはテキストを `79, 411` 、`x` 値を `84`、そして `y` 値を `89` にする必要があります。

```js
const labelFour = document.querySelectorAll('text')[3];
assert.strictEqual(labelFour?.textContent, '79, 411');
assert.strictEqual(labelFour?.getAttribute('x'), '84');
assert.strictEqual(labelFour?.getAttribute('y'), '89');
```

5 番目のラベルはテキストを `420, 220` 、`x` 値を `425`、そして `y` 値を `280` にする必要があります。

```js
const labelFive = document.querySelectorAll('text')[4];
assert.strictEqual(labelFive?.textContent, '420, 220');
assert.strictEqual(labelFive?.getAttribute('x'), '425');
assert.strictEqual(labelFive?.getAttribute('y'), '280');
```

6 番目のラベルはテキストを `233, 145` 、`x` 値を `238`、そして `y` 値を `355` にする必要があります。

```js
const labelSix = document.querySelectorAll('text')[5];
assert.strictEqual(labelSix?.textContent, '233, 145');
assert.strictEqual(labelSix?.getAttribute('x'), '238');
assert.strictEqual(labelSix?.getAttribute('y'), '355');
```

7 番目のラベルはテキストを `333, 96` 、`x` 値を `338`、そして `y` 値を `404` にする必要があります。

```js
const labelSeven = document.querySelectorAll('text')[6];
assert.strictEqual(labelSeven?.textContent, '333, 96');
assert.strictEqual(labelSeven?.getAttribute('x'), '338');
assert.strictEqual(labelSeven?.getAttribute('y'), '404');
```

8 番目のラベルはテキストを `222, 333`、`x` 値を `227`、そして `y` 値を `167` にする必要があります。

```js
const labelEight = document.querySelectorAll('text')[7];
assert.strictEqual(labelEight?.textContent, '222, 333');
assert.strictEqual(labelEight?.getAttribute('x'), '227');
assert.strictEqual(labelEight?.getAttribute('y'), '167');
```

9 番目のラベルはテキストを `78, 320` 、`x` 値を `83`、そして `y` 値を `180` にする必要があります。

```js
const labelNine = document.querySelectorAll('text')[8];
assert.strictEqual(labelNine?.textContent, '78, 320');
assert.strictEqual(labelNine?.getAttribute('x'), '83');
assert.strictEqual(labelNine?.getAttribute('y'), '180');
```

10 番目のラベルはテキストを `21, 123` 、`x` 値を `26`、そして `y` 値を `377` にする必要があります。

```js
const labelTen = document.querySelectorAll('text')[9];
assert.strictEqual(labelTen?.textContent, '21, 123');
assert.strictEqual(labelTen?.getAttribute('x'), '26');
assert.strictEqual(labelTen?.getAttribute('y'), '377');
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    const dataset = [
      [34, 78],
      [109, 280],
      [310, 120],
      [79, 411],
      [420, 220],
      [233, 145],
      [333, 96],
      [222, 333],
      [78, 320],
      [21, 123]
    ];

    const w = 500;
    const h = 500;

    const svg = d3
      .select('body')
      .append('svg')
      .attr('width', w)
      .attr('height', h);

    svg
      .selectAll('circle')
      .data(dataset)
      .enter()
      .append('circle')
      .attr('cx', (d, i) => d[0])
      .attr('cy', (d, i) => h - d[1])
      .attr('r', 5);

    svg.selectAll('text').data(dataset).enter().append('text');
    // Add your code below this line



    // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const dataset = [
      [34, 78],
      [109, 280],
      [310, 120],
      [79, 411],
      [420, 220],
      [233, 145],
      [333, 96],
      [222, 333],
      [78, 320],
      [21, 123]
    ];

    const w = 500;
    const h = 500;

    const svg = d3
      .select('body')
      .append('svg')
      .attr('width', w)
      .attr('height', h);

    svg
      .selectAll('circle')
      .data(dataset)
      .enter()
      .append('circle')
      .attr('cx', (d, i) => d[0])
      .attr('cy', (d, i) => h - d[1])
      .attr('r', 5);

    svg
      .selectAll('text')
      .data(dataset)
      .enter()
      .append('text')
      .attr('x', d => d[0] + 5)
      .attr('y', d => h - d[1])
      .text(d => d[0] + ', ' + d[1]);
  </script>
</body>
```
