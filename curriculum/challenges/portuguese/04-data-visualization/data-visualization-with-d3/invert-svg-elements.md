---
id: 587d7fa9367417b2b2512bd0
title: Inverter elementos do SVG
challengeType: 6
forumTopicId: 301488
dashedName: invert-svg-elements
---

# --description--

You may have noticed the bar chart looked like it's upside-down, or inverted. This is because of how SVG uses (x, y) coordinates.

No SVG, o ponto de origem para as coordenadas está no canto superior esquerdo. Uma coordenada `x` de 0 coloca uma forma na borda esquerda da área do SVG. Uma coordenada `y` de 0 coloca uma forma na borda superior da área do SVG. Valores mais altos de `x` empurram o retângulo para a direita. Valores mais altos de `y` empurram o retângulo para baixo.

Para fazer as barras ficarem na posição correta, você precisa alterar a maneira como a coordenada `y` é calculada. Isso precisa levar em conta tanto a altura da barra quanto a altura total da área do SVG.

A altura da área do SVG é 100. Se você tem um ponto de dados de 0 no conjunto, você deve esperar que a barra comece na parte inferior da área do SVG (não na parte superior). Para fazer isso, a coordenada `y` precisa de um valor de 100. Se o valor do ponto de dados for 1, você começaria com uma coordenada `y` de 100 para definir a barra na parte inferior. Em seguida, você precisa levar em conta a altura da barra de 1. Assim, a coordenada `y` final seria 99.

A coordenada `y` que é `y = heightOfSVG - heightOfBar` colocaria as barras na posição correta.

# --instructions--

Altere a função de callback para o atributo `y` para definir a posição das barras no lugar certo. Lembre-se de que a `height` da barra é 3 vezes o valor do dado `d`.

**Observação:** em geral, a relação é `y = h - m * d`, onde `m` é a constante que dimensiona os pontos de dados.

# --hints--

O primeiro `rect` deve ter um valor de `y` igual a `64`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[0]?.getAttribute('y'),
  (h - dataset[0] * 3).toString()
);
```

O segundo `rect` deve ter um valor de `y` igual a `7`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[1]?.getAttribute('y'),
  (h - dataset[1] * 3).toString()
);
```

O terceiro `rect` deve ter um valor de `y` igual a `34`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[2]?.getAttribute('y'),
  (h - dataset[2] * 3).toString()
);
```

O quarto `rect` deve ter um valor de `y` igual a `49`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[3]?.getAttribute('y'),
  (h - dataset[3] * 3).toString()
);
```

O quinto `rect` deve ter um valor de `y` igual a `25`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[4]?.getAttribute('y'),
  (h - dataset[4] * 3).toString()
);
```

O sexto `rect` deve ter um valor de `y` igual a `46`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[5]?.getAttribute('y'),
  (h - dataset[5] * 3).toString()
);
```

O sétimo `rect` deve ter um valor de `y` igual a `13`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[6]?.getAttribute('y'),
  (h - dataset[6] * 3).toString()
);
```

O oitavo `rect` deve ter um valor de `y` igual a `58`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[7]?.getAttribute('y'),
  (h - dataset[7] * 3).toString()
);
```

O nono `rect` deve ter um valor de `y` igual a `73`.

```js
assert.strictEqual(
  document.querySelectorAll('rect')[8]?.getAttribute('y'),
  (h - dataset[8] * 3).toString()
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
      .attr('y', (d, i) => {
        // Add your code below this line



        // Add your code above this line
      })
      .attr('width', 25)
      .attr('height', (d, i) => 3 * d);
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
      .attr('height', (d, i) => 3 * d);
  </script>
</body>
```
