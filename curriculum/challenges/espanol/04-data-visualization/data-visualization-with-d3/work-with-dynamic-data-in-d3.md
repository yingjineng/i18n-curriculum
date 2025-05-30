---
id: 587d7fa7367417b2b2512bc5
title: Trabaja con datos dinámicos en D3
challengeType: 6
forumTopicId: 301498
dashedName: work-with-dynamic-data-in-d3
---

# --description--

The last two challenges cover the basics of displaying data dynamically with D3 using the `data()` and `enter()` methods. These methods take a data set and, together with the `append()` method, create a new DOM element for each entry in the data set.

En el desafío anterior, haz creado un nuevo elemento `h2` para cada artículo en el arreglo `dataset`, pero todos contenían el mismo texto, `New Title`. Esto es porque no has usado los datos que están vinculados a cada uno de los elementos `h2`.

El método `text()` de D3 puede tomar una cadena o una función callback como argumento:

```js
selection.text(d => d);
```

En el ejemplo superior, el parámetro `d` hace referencia a una sola entrada en el conjunto de datos a la cual la selección está vinculada.

Utilizando el ejemplo actual como contexto, el primer elemento `h2` está vinculado a 12, el segundo elemento `h2` está vinculado a 31, el tercer elemento `h2` está vinculado a 22, y así sucesivamente.

# --instructions--

Cambia el método `text()` para que cada elemento `h2` muestre el valor correspondiente del arreglo `dataset` con un solo espacio y la cadena `USD`. Por ejemplo, el primer título debe ser `12 USD`.

# --hints--

El primer `h2` debe tener el texto `12 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[0]?.textContent, '12 USD');
```

El segundo `h2` debe tener el texto `31 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[1]?.textContent, '31 USD');
```

El tercer `h2` debe tener el texto `22 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[2]?.textContent, '22 USD');
```

El cuarto `h2` debe tener el texto `17 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[3]?.textContent, '17 USD');
```

El quinto `h2` debe tener el texto `25 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[4]?.textContent, '25 USD');
```

El sexto `h2` debe tener el texto `18 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[5]?.textContent, '18 USD');
```

El séptimo `h2` debe tener el texto `29 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[6]?.textContent, '29 USD');
```

El octavo `h2` debe tener el texto `14 USD`.

```js
assert.strictEqual(document.querySelectorAll('h2')[7]?.textContent, '14 USD');
```

El noveno `h2` debe tener el texto `9 USD`.

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
