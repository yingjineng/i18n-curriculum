---
id: 587d7faa367417b2b2512bd6
title: Füge einem D3-Element einen Tooltip hinzu
challengeType: 6
forumTopicId: 301470
dashedName: add-a-tooltip-to-a-d3-element
---

# --description--

A tooltip shows more information about an item on a page when the user hovers over that item. There are several ways to add a tooltip to a visualization. This challenge uses the SVG `title` element.

`title` wird mit der `text()`-Methode gekoppelt, um dynamisch Daten zu den Balken hinzuzufügen.

# --instructions--

Füge ein `title`-Element unter jedem `rect`-Punkt hinzu. Rufe dann die `text()`-Methode mit einer Callback-Funktion auf, so dass der Text den Datenwert anzeigt.

# --hints--

Dein Code sollte 9 `title`-Elemente haben.

```js
assert.lengthOf(document.querySelectorAll('title'), 9);
```

Das erste `title`-Element sollte einen Tooltip-Text von `12` haben.

```js
assert.strictEqual(document.querySelectorAll('title')[0]?.textContent, '12');
```

Das zweite `title`-Element sollte einen Tooltip-Text von `31` haben.

```js
assert.strictEqual(document.querySelectorAll('title')[1]?.textContent, '31');
```

Das dritte `title`-Element sollte einen Tooltip-Text von `22` haben.

```js
assert.strictEqual(document.querySelectorAll('title')[2]?.textContent, '22');
```

Das vierte `title`-Elemente sollte einen Tooltip-Text von `17` haben.

```js
assert.strictEqual(document.querySelectorAll('title')[3]?.textContent, '17');
```

Das fünfte `title`-Element sollte einen Tooltip-Text von `25` haben.

```js
assert.strictEqual(document.querySelectorAll('title')[4]?.textContent, '25');
```

Das sechste `title`-Element sollte einen Tooltip von `18` haben.

```js
assert.strictEqual(document.querySelectorAll('title')[5]?.textContent, '18');
```

Das siebte `title`-Element sollte einen Tooltip-Text von `29` haben.

```js
assert.strictEqual(document.querySelectorAll('title')[6]?.textContent, '29');
```

Das achte `title`-Element sollte einen Tooltip-Text von `14` haben.

```js
assert.strictEqual(document.querySelectorAll('title')[7]?.textContent, '14');
```

Das neunte `title`-Element sollte einen Tooltip-Text von `9` haben.

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
