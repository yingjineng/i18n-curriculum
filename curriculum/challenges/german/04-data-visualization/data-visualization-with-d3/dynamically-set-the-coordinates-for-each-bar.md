---
id: 587d7fa9367417b2b2512bce
title: Koordinaten für jeden Balken dynamisch festlegen
challengeType: 6
forumTopicId: 301487
dashedName: dynamically-set-the-coordinates-for-each-bar
---

# --description--

The last challenge created and appended a rectangle to the `svg` element for each point in `dataset` to represent a bar. Unfortunately, they were all stacked on top of each other.

Die Platzierung eines Rechtecks erfolgt über die `x`- und `y`-Attribute. Sie teilen D3 mit, wo mit der Platzierung der Form im `svg`-Bereich angefangen werden soll. In der letzten Aufgabe wurden sie alle auf 0 gesetzt, wodurch jeder Balken in der oberen linken Ecke landete.

Für ein Balkendiagramm sollten allerdings alle Balken auf derselben vertikalen Ebene platziert sein – der `y`-Wert eines jeden Balkens bleibt folglich auf 0. Jedoch muss sich der `x`-Wert mit jedem neuen Balken ändern. Denke daran, dass größere `x`-Werte die Elemente weiter nach rechts verschieben. Während du die Array-Elemente in `dataset` durchgehst, sollte der `x`-Wert steigen.

Die `attr()`-Methode in D3 akzeptiert eine Callback-Funktion, um dieses Attribut dynamisch zu setzen. Die Callback-Funktion benötigt zwei Argumente: eines für den Datenpunkt selbst (normalerweise `d`) und eines für den Index des Datenpunkts im Array. Das zweite Argument für den Index ist optional. Hier das Format:

```js
selection.attr('property', (d, i) => {});
```

Wichtig zu beachten ist, dass du weder eine `for`- noch eine `forEach()`-Schleife benötigst, um die Elemente im Datensatz zu durchlaufen. Denk daran, dass die `data()`-Methode den Datensatz analysiert und jede Methode, die nach `data()` verkettet ist, wird einmal für jedes Element im Datensatz ausgeführt.

# --instructions--

Verändere die Callback-Funktion für das `x`-Attribut so, dass diese den dreißigfachen Index zurückgibt.

**Hinweis:** Jeder Balken hat eine Breite von 25. Vergrößerst du also den `x`-Wert um 30, entsteht mehr Platz zwischen den Balken. Jeder Wert größer als 25 könnte in diesem Beispiel angewandt werden.

# --hints--

Das erste `rect` sollte über einen `x`-Wert von `0` verfügen.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[0]?.getAttribute('x'),
  '0'
);
```

Das zweite `rect` sollte über einen `x`-Wert von `30` verfügen.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[1]?.getAttribute('x'),
  '30'
);
```

Das dritte `rect` sollte über einen `x`-Wert von `60` verfügen.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[2]?.getAttribute('x'),
  '60'
);
```

Das vierte `rect` sollte über einen `x`-Wert von `90` verfügen.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[3]?.getAttribute('x'),
  '90'
);
```

Das fünfte `rect` sollte über einen `x`-Wert von `120` verfügen.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[4]?.getAttribute('x'),
  '120'
);
```

Das sechste `rect` sollte über einen `x`-Wert von `150` verfügen.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[5]?.getAttribute('x'),
  '150'
);
```

Das siebte `rect` sollte über einen `x`-Wert von `180` verfügen.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[6]?.getAttribute('x'),
  '180'
);
```

Das achte `rect` sollte über einen `x`-Wert von `210` verfügen.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[7]?.getAttribute('x'),
  '210'
);
```

Das neunte `rect` sollte über einen `x`-Wert von `240` verfügen.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[8]?.getAttribute('x'),
  '240'
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
      .attr('x', (d, i) => {
        // Add your code below this line



        // Add your code above this line
      })
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
      .attr('x', (d, i) => {
        return i * 30;
      })
      .attr('y', 0)
      .attr('width', 25)
      .attr('height', 100);
  </script>
</body>
```
