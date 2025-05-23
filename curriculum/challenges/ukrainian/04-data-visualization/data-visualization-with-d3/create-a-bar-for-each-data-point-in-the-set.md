---
id: 587d7fa8367417b2b2512bcd
title: Створіть стовпчик для кожної точки даних в наборі
challengeType: 6
forumTopicId: 301482
dashedName: create-a-bar-for-each-data-point-in-the-set
---

# --description--

The last challenge added only one rectangle to the `svg` element to represent a bar. Here, you'll combine what you've learned so far about `data()`, `enter()`, and SVG shapes to create and append a rectangle for each data point in `dataset`.

У попередньому завданні було пояснено, як створити та додати `div` для кожного елемента в `dataset`:

```js
d3.select('body')?.selectAll('div').data(dataset).enter().append('div');
```

Між роботою з елементами `rect` та `div` є певні відмінності. Елементи `rect` потрібно додавати до елемента `svg`, а не одразу до `body`. До того ж потрібно повідомити D3, де розміщувати кожен `rect` в межах площини `svg`. Ви дізнаєтесь про розміщення стовпчиків у наступному завданні.

# --instructions--

Використайте методи `data()`, `enter()` та `append()`, щоб створити та додати `rect` для кожного елемента в `dataset`. Стовпчики мають розміщуватись один на одному; це буде виправлено в наступному завданні.

# --hints--

Документ має містити 9 елементів `rect`.

```js
assert.lengthOf(document.querySelectorAll('rect'), 9);
```

Код має використати метод `data()`.

```js
assert.match(code, /\.data/g);
```

Код має використати метод `enter()`.

```js
assert.match(code, /\.enter/g);
```

Код має використати метод `append()`.

```js
assert.match(code, /\.append/g);
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
      // Add your code below this line

      // Add your code above this line
      .attr('x', 0)
      .attr('y', 0)
      .attr('width', 25)
      .attr('height', 100);
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
      .attr('x', 0)
      .attr('y', 0)
      .attr('width', 25)
      .attr('height', 100);
  </script>
</body>
```
