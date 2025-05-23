---
id: 587d7fa7367417b2b2512bc5
title: Lavorare con i dati dinamici in D3
challengeType: 6
forumTopicId: 301498
dashedName: work-with-dynamic-data-in-d3
---

# --description--

The last two challenges cover the basics of displaying data dynamically with D3 using the `data()` and `enter()` methods. These methods take a data set and, together with the `append()` method, create a new DOM element for each entry in the data set.

Nella sfida precedente, hai creato un nuovo elemento `h2` per ogni elemento nell'array `dataset`, ma tutti contenevano lo stesso testo, `New Title`. Questo perché non hai fatto uso dei dati che sono legati a ciascuno degli elementi `h2`.

Il metodo D3 `text()` può prendere una stringa o una funzione di callback come argomento:

```js
selection.text(d => d);
```

Nell'esempio precedente, il parametro `d` si riferisce a una singola voce nel set di dati a cui è associata una selezione.

Utilizzando l'esempio attuale come contesto, il primo elemento `h2` è legato a 12, il secondo elemento `h2` è legato a 31, il terzo elemento `h2` è legato a 22, e così via.

# --instructions--

Modifica il metodo `text()` in modo che ogni elemento `h2` mostri il valore corrispondente dall'array `dataset` con uno spazio e la stringa `USD`. Ad esempio, la prima intestazione dovrebbe essere `12 USD`.

# --hints--

Il primo `h2` dovrebbe avere il testo `12 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[0]?.textContent, '12 USD');
```

Il secondo `h2` dovrebbe avere il testo `31 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[1]?.textContent, '31 USD');
```

Il terzo `h2` dovrebbe avere il testo `22 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[2]?.textContent, '22 USD');
```

Il quarto `h2` dovrebbe avere il testo `17 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[3]?.textContent, '17 USD');
```

Il quinto `h2` dovrebbe avere il testo `25 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[4]?.textContent, '25 USD');
```

Il sesto `h2` dovrebbe avere il testo `18 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[5]?.textContent, '18 USD');
```

Il settimo `h2` dovrebbe avere il testo `29 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[6]?.textContent, '29 USD');
```

L'ottavo `h2` dovrebbe avere il testo `14 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[7]?.textContent, '14 USD');
```

Il nono `h2` dovrebbe avere il testo `9 USD`.

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
