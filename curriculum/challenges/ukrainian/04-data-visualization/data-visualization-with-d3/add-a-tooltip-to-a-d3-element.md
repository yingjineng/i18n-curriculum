---
id: 587d7faa367417b2b2512bd6
title: Додайте підказку до елемента D3
challengeType: 6
forumTopicId: 301470
dashedName: add-a-tooltip-to-a-d3-element
---

# --description--

A tooltip shows more information about an item on a page when the user hovers over that item. There are several ways to add a tooltip to a visualization. This challenge uses the SVG `title` element.

`title` працює разом з методом `text()`, щоб додати дані до стовпчиків динамічно.

# --instructions--

Додайте елемент `title` під кожен вузол `rect`. Потім викличте метод `text()` з функцією поверненого виклику, щоб текст показував значення даних.

# --hints--

Код має містити 9 елементів `title`.

```js
assert.lengthOf(document.querySelectorAll('title'), 9);
```

Текстом підказки першого елемента `title` має бути `12`.

```js
assert.strictEqual(document.querySelectorAll('title')[0]?.textContent, '12');
```

Текстом підказки другого елемента `title` має бути `31`.

```js
assert.strictEqual(document.querySelectorAll('title')[1]?.textContent, '31');
```

Текстом підказки третього елемента `title` має бути `22`.

```js
assert.strictEqual(document.querySelectorAll('title')[2]?.textContent, '22');
```

Текстом підказки четвертого елемента `title` має бути `17`.

```js
assert.strictEqual(document.querySelectorAll('title')[3]?.textContent, '17');
```

Текстом підказки п’ятого елемента `title` має бути `25`.

```js
assert.strictEqual(document.querySelectorAll('title')[4]?.textContent, '25');
```

Текстом підказки шостого елемента `title` має бути `18`.

```js
assert.strictEqual(document.querySelectorAll('title')[5]?.textContent, '18');
```

Текстом підказки сьомого елемента `title` має бути `29`.

```js
assert.strictEqual(document.querySelectorAll('title')[6]?.textContent, '29');
```

Текстом підказки восьмого елемента `title` має бути `14`.

```js
assert.strictEqual(document.querySelectorAll('title')[7]?.textContent, '14');
```

Текстом підказки дев’ятого елемента `title` має бути `9`.

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
