---
id: 587d7fa9367417b2b2512bcf
title: Змініть висоту кожного стовпчика динамічно
challengeType: 6
forumTopicId: 301486
dashedName: dynamically-change-the-height-of-each-bar
---

# --description--

The height of each bar can be set to the value of the data point in the array, similar to how the `x` value was set dynamically.

```js
selection.attr('property', (d, i) => {});
```

Тут `d` буде значенням точки даних, а `i` буде індексом точки даних у масиві.

# --instructions--

Змініть функцію зворотного виклику для атрибута `height`, щоб вона повернула значення даних, помножене на 3.

**Примітка:** пам’ятайте, що при множенні всіх даних змінюється масштабування даних (ніби збільшення). Це допомагає побачити різницю між значеннями стовпчиків у прикладі.

# --hints--

Перший `rect` повинен мати `height` зі значенням `36`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[0]?.getAttribute('height'),
  '36'
);
```

Другий `rect` повинен мати `height` зі значенням `93`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[1]?.getAttribute('height'),
  '93'
);
```

Третій `rect` повинен мати `height` зі значенням `66`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[2]?.getAttribute('height'),
  '66'
);
```

Четвертий `rect` повинен мати `height` зі значенням `51`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[3]?.getAttribute('height'),
  '51'
);
```

П’ятий `rect` повинен мати `height` зі значенням `75`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[4]?.getAttribute('height'),
  '75'
);
```

Шостий `rect` повинен мати `height` зі значенням `54`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[5]?.getAttribute('height'),
  '54'
);
```

Сьомий `rect` повинен мати `height` зі значенням `87`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[6]?.getAttribute('height'),
  '87'
);
```

Восьмий `rect` повинен мати `height` зі значенням `42`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[7]?.getAttribute('height'),
  '42'
);
```

Дев’ятий `rect` повинен мати `height` зі значенням `27`.

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
