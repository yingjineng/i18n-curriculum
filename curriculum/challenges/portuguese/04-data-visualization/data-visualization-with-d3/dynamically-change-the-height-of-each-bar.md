---
id: 587d7fa9367417b2b2512bcf
title: Alterar dinamicamente a altura de cada barra
challengeType: 6
forumTopicId: 301486
dashedName: dynamically-change-the-height-of-each-bar
---

# --description--

The height of each bar can be set to the value of the data point in the array, similar to how the `x` value was set dynamically.

```js
selection.attr('property', (d, i) => {});
```

Aqui, `d` seria o valor do ponto de dados, enquanto `i` seria o índice do ponto de dados no array.

# --instructions--

Altere a função de callback para o atributo `height` para que retorne o valor dos dados vezes 3.

**Observação:** lembre-se de que multiplicar todos os dados redimensiona os dados (como se déssemos um zoom). Neste exemplo, ajuda a ver as diferenças entre os valores da barra.

# --hints--

O primeiro `rect` deve ter uma `height` de `36`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[0]?.getAttribute('height'),
  '36'
);
```

O segundo `rect` deve ter uma `height` de `93`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[1]?.getAttribute('height'),
  '93'
);
```

O terceiro `rect` deve ter uma `height` de `66`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[2]?.getAttribute('height'),
  '66'
);
```

O quarto `rect` deve ter uma `height` de `51`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[3]?.getAttribute('height'),
  '51'
);
```

O quinto `rect` deve ter uma `height` de `75`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[4]?.getAttribute('height'),
  '75'
);
```

O sexto `rect` deve ter uma `height` de `54`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[5]?.getAttribute('height'),
  '54'
);
```

O sétimo `rect` deve ter uma `height` de `87`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[6]?.getAttribute('height'),
  '87'
);
```

O oitavo `rect` deve ter uma `height` de `42`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[7]?.getAttribute('height'),
  '42'
);
```

O nono `rect` deve ter uma `height` de `27`.

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
