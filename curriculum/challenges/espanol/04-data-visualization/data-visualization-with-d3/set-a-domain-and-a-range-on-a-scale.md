---
id: 587d7fac367417b2b2512bdb
title: Establece un dominio y un rango en una escala
challengeType: 6
forumTopicId: 301491
dashedName: set-a-domain-and-a-range-on-a-scale
---

# --description--

By default, scales use the identity relationship. This means the input value maps to the output value. However, scales can be much more flexible and interesting.

Digamos que un conjunto de datos tiene valores entre 50 y 480. Esta es la información de entrada para una escala, también conocido como el <dfn>dominio</dfn>.

Desea asignar esos puntos a lo largo del eje `x` en el SVG, entre 10 unidades y 500 unidades. Esta es la información de salida, también conocida como el <dfn>rango</dfn>.

Los métodos `domain()` y `range()` establecen estos valores para la escala. Ambos métodos toman un arreglo de al menos dos elementos como argumento. Aquí un ejemplo:

```js
scale.domain([50, 480]);
scale.range([10, 500]);
scale(50);
scale(480);
scale(325);
scale(750);
d3.scaleLinear();
```

En orden, los siguientes valores se mostrarían en la consola: `10`, `500`, `323.37`, y `807.67`.

Observa que la escala usa la relación lineal entre los valores del dominio y del rango para averiguar cuál debe ser la salida para un número dado. El valor mínimo en el dominio (50) se asigna al valor mínimo (10) en el rango.

# --instructions--

Crea una escala y establece su dominio a `[250, 500]` y su rango a `[10, 150]`.

**Nota:** Puedes encadenar los métodos `domain()` y `range()` a la variable `scale`.

# --hints--

Tu código debe usar el método `domain()`.

```js
assert.match(code, /\.domain/g);
```

El `domain()` de `scale` (escala) debe ser establecido a `[250, 500]`.

```js
assert.deepEqual(scale.domain(), [250, 500]);
```

Tu código debe usar el método `range()`.

```js
assert.match(code, /\.range/g);
```

El `range()` de `scale` (escala) debe ser establecido a `[10, 150]`.

```js
assert.deepEqual(scale.range(), [10, 150]);
```

El texto en el `h2` debe ser `-102`.

```js
assert.strictEqual(document.querySelector('h2')?.textContent, '-102');
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    // Add your code below this line
    const scale = d3.scaleLinear();



    // Add your code above this line
    const output = scale(50);
    d3.select('body').append('h2').text(output);
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const scale = d3.scaleLinear();
    scale.domain([250, 500]);
    scale.range([10, 150]);
    const output = scale(50);
    d3.select('body').append('h2').text(output);
  </script>
</body>
```
