---
id: 587d7faa367417b2b2512bd3
title: Стилізуйте позначки D3
challengeType: 6
forumTopicId: 301492
dashedName: style-d3-labels
---

# --description--

D3 methods can add styles to the bar labels. The `fill` attribute sets the color of the text for a `text` node. The `style()` method sets CSS rules for other styles, such as `font-family` or `font-size`.

# --instructions--

Встановіть `font-size` елементів `text` на `25px`, а колір тексту — на червоний.

# --hints--

Позначки повинні мати `fill` зі значенням червоного кольору.

```js
const text = document.querySelector('text');
assert.exists(text); 
const fill = window.getComputedStyle(text)['fill'];
assert.strictEqual(fill, 'rgb(255, 0, 0)');
```

Позначки повинні мати `font-size` зі значенням `25` пікселів.

```js
const text = document.querySelector('text');
assert.exists(text); 
const fontSize = window.getComputedStyle(text)['font-size'];
assert.strictEqual(fontSize, '25px');
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
      .attr('height', (d, i) => d * 3)
      .attr('fill', 'navy');

    svg
      .selectAll('text')
      .data(dataset)
      .enter()
      .append('text')
      .text(d => d)
      .attr('x', (d, i) => i * 30)
      .attr('y', (d, i) => h - 3 * d - 3);
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
      .attr('height', (d, i) => d * 3)
      .attr('fill', 'navy');

    svg
      .selectAll('text')
      .data(dataset)
      .enter()
      .append('text')
      .text(d => d)
      .attr('x', (d, i) => i * 30)
      .attr('y', (d, i) => h - 3 * d - 3)
      .style('font-size', 25)
      .attr('fill', 'red');
  </script>
</body>
```
