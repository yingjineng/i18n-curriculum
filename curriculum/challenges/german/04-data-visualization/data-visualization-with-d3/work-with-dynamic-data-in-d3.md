---
id: 587d7fa7367417b2b2512bc5
title: Mit Dynamischen Daten in D3 arbeiten
challengeType: 6
forumTopicId: 301498
dashedName: work-with-dynamic-data-in-d3
---

# --description--

The last two challenges cover the basics of displaying data dynamically with D3 using the `data()` and `enter()` methods. These methods take a data set and, together with the `append()` method, create a new DOM element for each entry in the data set.

In der vorherigen Aufgabe hast du ein neues `h2`-Element für jeden Eintrag des `dataset`-Arrays erstellt – diese beinhalteten jedoch alle den gleichen Text, `New Title`. Das liegt daran, dass du die Daten, die an jedes der `h2`-Elemente gebunden sind, nicht verwendet hast.

Die `text()`-Methode von D3 kann sowohl mit einem String als auch mit einer Callback-Funktion als Argument arbeiten:

```js
selection.text(d => d);
```

Im obigen Beispiel bezieht sich der Parameter `d` auf einen einzelnen Eintrag im Dataset, an den eine Auswahl gebunden ist.

Wenn man das aktuelle Beispiel im Kontext verwenden, dann ist das erste `h2`-Element an 12 gebunden, das zweite `h2`-Element an 31, das dritte `h2`-Element an 22, und so weiter.

# --instructions--

Ändere die `text()`-Methode so, dass jedes `h2`-Element den dazugehörigen Wert des `dataset`-Arrays mit einem einzigen Leerzeichen und den String `USD` anzeigt. Zum Beispiel sollte die erste Überschrift `12 USD` sein.

# --hints--

Das erste `h2`-Element sollte aus dem Text `12 USD` bestehen.

```js
assert.strictEqual(document.querySelectorAll('h2')[0]?.textContent, '12 USD');
```

Das zweite `h2`-Element sollte aus dem Text `31 USD` bestehen.

```js
assert.strictEqual(document.querySelectorAll('h2')[1]?.textContent, '31 USD');
```

Das dritte `h2`-Element sollte aus dem Text `22 USD` bestehen.

```js
assert.strictEqual(document.querySelectorAll('h2')[2]?.textContent, '22 USD');
```

Das vierte `h2`-Element sollte aus dem Text `17 USD` bestehen.

```js
assert.strictEqual(document.querySelectorAll('h2')[3]?.textContent, '17 USD');
```

Das fünfte `h2`-Element sollte aus dem Text `25 USD` bestehen.

```js
assert.strictEqual(document.querySelectorAll('h2')[4]?.textContent, '25 USD');
```

Das sechste `h2`-Element sollte aus dem Text `18 USD` bestehen.

```js
assert.strictEqual(document.querySelectorAll('h2')[5]?.textContent, '18 USD');
```

Das siebte `h2`-Element sollte aus dem Text `29 USD` bestehen.

```js
assert.strictEqual(document.querySelectorAll('h2')[6]?.textContent, '29 USD');
```

Das achte `h2`-Element sollte aus dem Text `14 USD` bestehen.

```js
assert.strictEqual(document.querySelectorAll('h2')[7]?.textContent, '14 USD');
```

Das neunte `h2`-Element sollte aus dem Text `9 USD` bestehen.

```js
assert.strictEqual(document.querySelectorAll('h2')[8]?.textContent, '9 USD');
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    d3.select('body')
      .selectAll('h2')
      .data(dataset)
      .enter()
      .append('h2')
      // Add your code below this line

      .text('New Title');

    // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    d3.select('body')
      .selectAll('h2')
      .data(dataset)
      .enter()
      .append('h2')
      .text(d => `${d} USD`);
  </script>
</body>
```
