---
id: 587d7fab367417b2b2512bda
title: Crea una escala lineal con D3
challengeType: 6
forumTopicId: 301483
dashedName: create-a-linear-scale-with-d3
---

# --description--

The bar and scatter plot charts both plotted data directly onto the SVG. However, if the height of a bar or one of the data points were larger than the SVG height or width values, it would go outside the SVG area.

En D3, hay escalas para ayudar a trazar datos. `scales` son funciones que le dicen al programa cómo asignar un conjunto de puntos de datos sin procesar a los pixeles del SVG.

Por ejemplo, digamos que tienes un lienzo SVG de tamaño 100X500 y quieres trazar el Producto Interior Bruto para un número de países. El conjunto de números estaría en el rango de miles de millones o billones de dólares. Tú le provees a D3 un tipo de escala para decirle cómo colocar los grandes valores de PBI en esa área de tamaño 100x500.

Es muy poco probable que traces los datos en bruto tal como son. Antes de trazarlo, estableces la escala para todo el conjunto de datos, de modo que los valores `x` y `y` se ajusten al ancho y altura de tu SVG.

D3 tiene varios tipos de escalas. Para una escala lineal (usualmente usada con datos cuantitativos), existe el método de D3 `scaleLinear()`:

```js
const scale = d3.scaleLinear();
```

Por defecto, una escala usa la relación de identidad. El valor de la entrada es el mismo que el valor de la salida. Un desafío aparte cubre como cambiar esto.

# --instructions--

Cambia la variable `scale` para crear una escala lineal. Luego, establece la variable `output` a la escala llamada, con un argumento de entrada (input) de `50`.

# --hints--

El texto en el `h2` debe ser `50`.

```js
assert.strictEqual(document.querySelector('h2')?.textContent, '50');
```

Tu código debe utilizar el método `scaleLinear()`.

```js
assert.match(code, /\.scaleLinear/g);
```

La variable `output` debe llamar a `scale` con un argumento de `50`.

```js
assert.strictEqual(output, 50);
assert.match(code, /scale\(\s*50\s*\)/g);
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    // Add your code below this line

    const scale = undefined; // Create the scale here
    const output = scale(); // Call scale with an argument here

    // Add your code above this line

    d3.select('body').append('h2').text(output);
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const scale = d3.scaleLinear();
    const output = scale(50);

    d3.select('body').append('h2').text(output);
  </script>
</body>
```
