---
id: 587d7fac367417b2b2512bde
title: Usar uma escala predefinida para definir o local dos elementos
challengeType: 6
forumTopicId: 301494
dashedName: use-a-pre-defined-scale-to-place-elements
---

# --description--

With the scales set up, it's time to map the scatter plot again. The scales are like processing functions that turn the `x` and `y` raw data into values that fit and render correctly on the SVG. They keep the data within the screen's plotting area.

Você define os valores dos atributos das coordenadas para uma forma do SVG com a função de dimensionamento. Isso inclui os atributos `x` e `y` para `rect`, elementos `text`, ou `cx` e `cy` para `circles`. Exemplo:

```js
shape.attr('x', d => xScale(d[0]));
```

As escalas definem atributos de coordenadas de forma a colocar os pontos de dados no SVG. Você não precisa aplicar as escalas quando exibir o valor real dos dados, por exemplo, no método `text()` para uma dica ou etiqueta.

# --instructions--

Use `xScale` e `yScale` para posicionar ambas as formas, `circle` e `text`, no SVG. Para os `circles`, aplique as escalas para definir os atributos `cx` e `cy`. Dê a elas um raio de `5` unidades, também.

Para os elementos `text`, aplique as escalas para definir os atributos `x` e `y`. As etiquetas devem ser deslocadas para a direita dos pontos. Para fazer isso, adicione `10` unidades ao valor de `x` dos dados antes de passá-lo para `xScale`.

# --hints--

O código deve ter 10 elementos `circle`.

```js
assert.lengthOf(document.querySelectorAll('circle'), 10);
```

O primeiro elemento `circle` deve ter um valor de `cx` de aproximadamente `91` e um valor de `cy` de aproximadamente `368` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const firstCircle = document.querySelectorAll('circle')[0];
assert.strictEqual(Math.round(firstCircle?.getAttribute('cx')), 91);
assert.strictEqual(Math.round(firstCircle?.getAttribute('cy')), 368);
assert.strictEqual(Math.round(firstCircle?.getAttribute('r')), 5);
```

O segundo elemento `circle` deve ter um valor de `cx` de aproximadamente `159` e um valor de `cy` de aproximadamente `181` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const secondCircle = document.querySelectorAll('circle')[1];
assert.strictEqual(Math.round(secondCircle?.getAttribute('cx')), 159);
assert.strictEqual(Math.round(secondCircle?.getAttribute('cy')), 181);
assert.strictEqual(Math.round(secondCircle?.getAttribute('r')), 5);
```

O terceiro elemento `circle` deve ter um valor de `cx` de aproximadamente `340` e um valor de `cy` de aproximadamente `329` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const thirdCircle = document.querySelectorAll('circle')[2];
assert.strictEqual(Math.round(thirdCircle?.getAttribute('cx')), 340);
assert.strictEqual(Math.round(thirdCircle?.getAttribute('cy')), 329);
assert.strictEqual(Math.round(thirdCircle?.getAttribute('r')), 5);
```

O quarto elemento `circle` deve ter um valor de `cx` de aproximadamente `131` e um valor de `cy` de aproximadamente `60` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const fourthCircle = document.querySelectorAll('circle')[3];
assert.strictEqual(Math.round(fourthCircle?.getAttribute('cx')), 131);
assert.strictEqual(Math.round(fourthCircle?.getAttribute('cy')), 60);
assert.strictEqual(Math.round(fourthCircle?.getAttribute('r')), 5);
```

O quinto elemento `circle` deve ter um valor de `cx` de aproximadamente `440` e um valor de `cy` de aproximadamente `237` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const fifthCircle = document.querySelectorAll('circle')[4];
assert.strictEqual(Math.round(fifthCircle?.getAttribute('cx')), 440);
assert.strictEqual(Math.round(fifthCircle?.getAttribute('cy')), 237);
assert.strictEqual(Math.round(fifthCircle?.getAttribute('r')), 5);
```

O sexto elemento `circle` deve ter um valor de `cx` de aproximadamente `271` e um valor de `cy` de aproximadamente `306` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const sixthCircle = document.querySelectorAll('circle')[5];
assert.strictEqual(Math.round(sixthCircle?.getAttribute('cx')), 271);
assert.strictEqual(Math.round(sixthCircle?.getAttribute('cy')), 306);
assert.strictEqual(Math.round(sixthCircle?.getAttribute('r')), 5);
```

O sétimo elemento `circle` deve ter um valor de `cx` de aproximadamente `361` e um valor de `cy` de aproximadamente `351` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const seventhCircle = document.querySelectorAll('circle')[6];
assert.strictEqual(Math.round(seventhCircle?.getAttribute('cx')), 361);
assert.strictEqual(Math.round(seventhCircle?.getAttribute('cy')), 351);
assert.strictEqual(Math.round(seventhCircle?.getAttribute('r')), 5);
```

O oitavo elemento `circle` deve ter um valor de `cx` de aproximadamente `261` e um valor de `cy` de aproximadamente `132` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const eighthCircle = document.querySelectorAll('circle')[7];
assert.strictEqual(Math.round(eighthCircle?.getAttribute('cx')), 261);
assert.strictEqual(Math.round(eighthCircle?.getAttribute('cy')), 132);
assert.strictEqual(Math.round(eighthCircle?.getAttribute('r')), 5);
```

O nono elemento `circle` deve ter um valor de `cx` de aproximadamente `131` e um valor de `cy` de aproximadamente `144` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const ninthCircle = document.querySelectorAll('circle')[8];
assert.strictEqual(Math.round(ninthCircle?.getAttribute('cx')), 131);
assert.strictEqual(Math.round(ninthCircle?.getAttribute('cy')), 144);
assert.strictEqual(Math.round(ninthCircle?.getAttribute('r')), 5);
```

O décimo elemento `circle` deve ter um valor de `cx` de aproximadamente `79` e um valor de `cy` de aproximadamente `326` após a aplicação das escalas. Ele também deve ter um valor `r` de `5`.

```js
const tenthCircle = document.querySelectorAll('circle')[9];
assert.strictEqual(Math.round(tenthCircle?.getAttribute('cx')), 79);
assert.strictEqual(Math.round(tenthCircle?.getAttribute('cy')), 326);
assert.strictEqual(Math.round(tenthCircle?.getAttribute('r')), 5);
```

O código deve ter 10 elementos `text`.

```js
assert.lengthOf(document.querySelectorAll('text'), 10);
```

A primeira etiqueta deve ter um valor de `x` de aproximadamente `100` e um valor de `y` de aproximadamente `368` após aplicar as escalas.

```js
const firstLabel = document.querySelectorAll('text')[0];
assert.strictEqual(Math.round(firstLabel?.getAttribute('x')), 100);
assert.strictEqual(Math.round(firstLabel?.getAttribute('y')), 368);
```

A segunda etiqueta deve ter um valor de `x` de aproximadamente `168` e um valor de `y` de aproximadamente `181` após aplicar as escalas.

```js
const secondLabel = document.querySelectorAll('text')[1];
assert.strictEqual(Math.round(secondLabel?.getAttribute('x')), 168);
assert.strictEqual(Math.round(secondLabel?.getAttribute('y')), 181);
```

A terceira etiqueta deve ter um valor de `x` de aproximadamente `350` e um valor de `y` de aproximadamente `329` após aplicar as escalas.

```js
const thirdLabel = document.querySelectorAll('text')[2];
assert.strictEqual(Math.round(thirdLabel?.getAttribute('x')), 350);
assert.strictEqual(Math.round(thirdLabel?.getAttribute('y')), 329);
```

A quarta etiqueta deve ter um valor de `x` de aproximadamente `141` e um valor de `y` de aproximadamente `60` após aplicar as escalas.

```js
const fourthLabel = document.querySelectorAll('text')[3];
assert.strictEqual(Math.round(fourthLabel?.getAttribute('x')), 141);
assert.strictEqual(Math.round(fourthLabel?.getAttribute('y')), 60);
```

A quinta etiqueta deve ter um valor de `x` de aproximadamente `449` e um valor de `y` de aproximadamente `237` após aplicar as escalas.

```js
const fifthLabel = document.querySelectorAll('text')[4];
assert.strictEqual(Math.round(fifthLabel?.getAttribute('x')), 449);
assert.strictEqual(Math.round(fifthLabel?.getAttribute('y')), 237);
```

A sexta etiqueta deve ter um valor de `x` de aproximadamente `280` e um valor de `y` de aproximadamente `306` após aplicar as escalas.

```js
const sixthLabel = document.querySelectorAll('text')[5];
assert.strictEqual(Math.round(sixthLabel?.getAttribute('x')), 280);
assert.strictEqual(Math.round(sixthLabel?.getAttribute('y')), 306);
```

A sétima etiqueta deve ter um valor de `x` de aproximadamente `370` e um valor de `y` de aproximadamente `351` após aplicar as escalas.

```js
const seventhLabel = document.querySelectorAll('text')[6];
assert.strictEqual(Math.round(seventhLabel?.getAttribute('x')), 370);
assert.strictEqual(Math.round(seventhLabel?.getAttribute('y')), 351);
```

A oitava etiqueta deve ter um valor de `x` de aproximadamente `270` e um valor de `y` de aproximadamente `132` após aplicar as escalas.

```js
const eighthLabel = document.querySelectorAll('text')[7];
assert.strictEqual(Math.round(eighthLabel?.getAttribute('x')), 270);
assert.strictEqual(Math.round(eighthLabel?.getAttribute('y')), 132);
```

A nona etiqueta deve ter um valor de `x` de aproximadamente `140` e um valor de `y` de aproximadamente `144` após aplicar as escalas.

```js
const ninthLabel = document.querySelectorAll('text')[8];
assert.strictEqual(Math.round(ninthLabel?.getAttribute('x')), 140);
assert.strictEqual(Math.round(ninthLabel?.getAttribute('y')), 144);
```

A décima etiqueta deve ter um valor de `x` de aproximadamente `88` e um valor de `y` de aproximadamente `326` após aplicar as escalas.

```js
const tenthLabel = document.querySelectorAll('text')[9];
assert.strictEqual(Math.round(tenthLabel?.getAttribute('x')), 88);
assert.strictEqual(Math.round(tenthLabel?.getAttribute('y')), 326);
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    const dataset = [
      [34, 78],
      [109, 280],
      [310, 120],
      [79, 411],
      [420, 220],
      [233, 145],
      [333, 96],
      [222, 333],
      [78, 320],
      [21, 123]
    ];

    const w = 500;
    const h = 500;
    const padding = 60;

    const xScale = d3
      .scaleLinear()
      .domain([0, d3.max(dataset, d => d[0])])
      .range([padding, w - padding]);

    const yScale = d3
      .scaleLinear()
      .domain([0, d3.max(dataset, d => d[1])])
      .range([h - padding, padding]);

    const svg = d3
      .select('body')
      .append('svg')
      .attr('width', w)
      .attr('height', h);

    svg.selectAll('circle').data(dataset).enter().append('circle');
    // Add your code below this line



    // Add your code above this line

    svg
      .selectAll('text')
      .data(dataset)
      .enter()
      .append('text')
      .text(d => d[0] + ', ' + d[1]);
    // Add your code below this line

    // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const dataset = [
      [34, 78],
      [109, 280],
      [310, 120],
      [79, 411],
      [420, 220],
      [233, 145],
      [333, 96],
      [222, 333],
      [78, 320],
      [21, 123]
    ];

    const w = 500;
    const h = 500;
    const padding = 60;

    const xScale = d3
      .scaleLinear()
      .domain([0, d3.max(dataset, d => d[0])])
      .range([padding, w - padding]);

    const yScale = d3
      .scaleLinear()
      .domain([0, d3.max(dataset, d => d[1])])
      .range([h - padding, padding]);

    const svg = d3
      .select('body')
      .append('svg')
      .attr('width', w)
      .attr('height', h);

    svg
      .selectAll('circle')
      .data(dataset)
      .enter()
      .append('circle')
      .attr('cx', d => xScale(d[0]))
      .attr('cy', d => yScale(d[1]))
      .attr('r', 5);

    svg
      .selectAll('text')
      .data(dataset)
      .enter()
      .append('text')
      .text(d => d[0] + ', ' + d[1])
      .attr('x', d => xScale(d[0] + 10))
      .attr('y', d => yScale(d[1]));
  </script>
</body>
```
