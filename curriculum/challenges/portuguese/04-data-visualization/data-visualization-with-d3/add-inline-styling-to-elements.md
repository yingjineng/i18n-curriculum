---
id: 587d7fa7367417b2b2512bc6
title: Adicionar estilo em linha aos elementos
challengeType: 6
forumTopicId: 301475
dashedName: add-inline-styling-to-elements
---

# --description--

D3 lets you add inline CSS styles on dynamic elements with the `style()` method.

O método `style()` receb um par chave-valor separado por vírgulas como argumento. Aqui está um exemplo para definir a cor do texto da seleção como azul:

```js
selection.style('color', 'blue');
```

# --instructions--

Adicione o método `style()` ao código no editor para fazer com que todo o texto exibido tenha a `font-family` `verdana`.

# --hints--

Os elementos `h2` devem ter a propriedade `font-family` `verdana`.

```js
const headingTwo = document.querySelector('h2');
assert.exists(headingTwo); 
const fontFamily = window.getComputedStyle(headingTwo)['font-family'];
assert.strictEqual(fontFamily, 'verdana');
```

O código deve usar o método `style()`.

```js
assert.match(code, /\.style/g);
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
      .text(d => d + ' USD');
    // Add your code below this line



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
      .text(d => d + ' USD')
      .style('font-family', 'verdana');
  </script>
</body>
```
