---
id: 587d7fa9367417b2b2512bd1
title: Змініть колір елемента SVG
challengeType: 6
forumTopicId: 301480
dashedName: change-the-color-of-an-svg-element
---

# --description--

The bars are in the right position, but they are all the same black color. SVG has a way to change the color of the bars.

Фігура `rect` в SVG зафарбована завдяки атрибуту `fill`. Він підтримує шістнадцяткові коди, назви кольорів та значення rgb, а також складніші варіанти, серед яких градієнт та прозорість.

# --instructions--

Додайте метод `attr()`, щоб встановити `fill` всіх стовпчиків на синій колір.

# --hints--

Стовпчики повинні мати `fill` зі значенням синього кольору.

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
