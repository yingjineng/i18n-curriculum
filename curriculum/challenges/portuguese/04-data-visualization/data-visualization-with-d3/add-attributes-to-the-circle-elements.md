---
id: 587d7fab367417b2b2512bd8
title: Adicionar atributos aos elementos de círculo
challengeType: 6
forumTopicId: 301471
dashedName: add-attributes-to-the-circle-elements
---

# --description--

The last challenge created the `circle` elements for each point in the `dataset`, and appended them to the SVG. But D3 needs more information about the position and size of each `circle` to display them correctly.

Um `circle` em SVG tem três atributos principais. Os atributos `cx` e `cy` são as coordenadas. They tell D3 where to position the _center_ of the shape on the SVG. O raio (atributo `r`) fornece o tamanho de `circle`.

Assim como ocorre com `rect`, em sua coordenada `y`, o atributo `cy` de um `circle` é medido do topo do SVG, não da parte inferior.

Todos os três atributos podem usar uma função de callback para definir seus valores dinamicamente. Lembre-se de que todos os métodos encadeados após `data(dataset)` são executados uma vez por item no `dataset`. O parâmetro `d` na função de callback se refere ao item atual no `dataset`, que é um array para aquele ponto. Use a notação de colchetes, por exemplo `d[0]`, para acessar valores naquele array.

# --instructions--

Adicione os atributos `cx`, `cy` e `r` aos elementos `circle`. O valor de `cx` deve ser o primeiro número do array para cada item no `dataset`. O valor de `cy` deve ser baseado no segundo número do array, mas certifique-se de mostrar o gráfico voltado para o lado certo, em vez de invertido. O valor de `r` deve ser `5` para todos os círculos.

# --hints--

O código deve ter 10 elementos `circle`.

```js
assert.lengthOf(document.querySelectorAll('circle'), 10);
```

O primeiro elemento `circle` deve ter um valor `cx` de `34`, um valor `cy` de `422` e um valor `r` de `5`.

```js
const circle1 = document.querySelector('circle');
assert.strictEqual(circle1?.getAttribute('cx'), '34');
assert.strictEqual(circle1?.getAttribute('cy'), '422');
assert.strictEqual(circle1?.getAttribute('r'), '5');
```

O segundo elemento `circle` deve ter um valor `cx` de `109`, um valor `cy` de `220` e um valor `r` de `5`.

```js
const circle2 = document.querySelectorAll('circle')[1];
assert.strictEqual(circle2?.getAttribute('cx'), '109');
assert.strictEqual(circle2?.getAttribute('cy'), '220');
assert.strictEqual(circle2?.getAttribute('r'), '5');
```

O terceiro elemento `circle` deve ter um valor `cx` de `310`, um valor `cy` de `380` e um valor `r` de `5`.

```js
const circle3 = document.querySelectorAll('circle')[2];
assert.strictEqual(circle3?.getAttribute('cx'), '310');
assert.strictEqual(circle3?.getAttribute('cy'), '380');
assert.strictEqual(circle3?.getAttribute('r'), '5');
```

O quarto elemento `circle` deve ter um valor `cx` de `79`, um valor `cy` de `89` e um valor `r` de `5`.

```js
const circle4 = document.querySelectorAll('circle')[3];
assert.strictEqual(circle4?.getAttribute('cx'), '79');
assert.strictEqual(circle4?.getAttribute('cy'), '89');
assert.strictEqual(circle4?.getAttribute('r'), '5');
```

O quinto elemento `circle` deve ter um valor `cx` de `420`, um valor `cy` de `280` e um valor `r` de `5`.

```js
const circle5 = document.querySelectorAll('circle')[4];
assert.strictEqual(circle5?.getAttribute('cx'), '420');
assert.strictEqual(circle5?.getAttribute('cy'), '280');
assert.strictEqual(circle5?.getAttribute('r'), '5');
```

O sexto elemento `circle` deve ter um valor `cx` de `233`, um valor `cy` de `355` e um valor `r` de `5`.

```js
const circle6 = document.querySelectorAll('circle')[5];
assert.strictEqual(circle6?.getAttribute('cx'), '233');
assert.strictEqual(circle6?.getAttribute('cy'), '355');
assert.strictEqual(circle6?.getAttribute('r'), '5');
```

O sétimo elemento `circle` deve ter um valor `cx` de `333`, um valor `cy` de `404` e um valor `r` de `5`.

```js
const circle7 = document.querySelectorAll('circle')[6];
assert.strictEqual(circle7?.getAttribute('cx'), '333');
assert.strictEqual(circle7?.getAttribute('cy'), '404');
assert.strictEqual(circle7?.getAttribute('r'), '5');
```

O oitavo elemento `circle` deve ter um valor `cx` de `222`, um valor `cy` de `167` e um valor `r` de `5`.

```js
const circle8 = document.querySelectorAll('circle')[7];
assert.strictEqual(circle8?.getAttribute('cx'), '222');
assert.strictEqual(circle8?.getAttribute('cy'), '167');
assert.strictEqual(circle8?.getAttribute('r'), '5');
```

O nono elemento `circle` deve ter um valor `cx` de `78`, um valor `cy` de `180` e um valor `r` de `5`.

```js
const circle9 = document.querySelectorAll('circle')[8];
assert.strictEqual(circle9?.getAttribute('cx'), '78');
assert.strictEqual(circle9?.getAttribute('cy'), '180');
assert.strictEqual(circle9?.getAttribute('r'), '5');
```

O décimo elemento `circle` deve ter um valor `cx` de `21`, um valor `cy` de `377` e um valor `r` de `5`.

```js
const circle10 = document.querySelectorAll('circle')[9];
assert.strictEqual(circle10?.getAttribute('cx'), '21');
assert.strictEqual(circle10?.getAttribute('cy'), '377');
assert.strictEqual(circle10?.getAttribute('r'), '5');
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

    const svg = d3
      .select('body')
      .append('svg')
      .attr('width', w)
      .attr('height', h);

    svg.selectAll('circle').data(dataset).enter().append('circle');
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
      .attr('cx', d => d[0])
      .attr('cy', d => h - d[1])
      .attr('r', 5);
  </script>
</body>
```
