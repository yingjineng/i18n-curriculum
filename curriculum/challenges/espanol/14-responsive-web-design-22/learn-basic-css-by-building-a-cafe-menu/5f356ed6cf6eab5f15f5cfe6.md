---
id: 5f356ed6cf6eab5f15f5cfe6
title: Paso 20
challengeType: 0
dashedName: step-20
---

# --description--

El elemento `div` se utiliza principalmente para propósitos de diseño, a diferencia de los otros elementos de contenido que has usado hasta ahora. Añade un elemento `div` dentro del elemento `body` y luego mueve todos los demás elementos dentro del nuevo `div`.

Dentro de la etiqueta `div` de apertura, añade el atributo `id` con un valor de `menu`.

# --hints--

Tu etiqueta `<div>` de apertura debe tener un atributo `id` establecido en `menu`.

```js
assert.strictEqual(document.querySelector('div')?.id, 'menu');
```

Debes tener una etiqueta `</div>` de cierre.

```js
assert(code.match(/<\/div>/i));
```

No debes cambiar tu elemento `body` existente. Asegúrate de no haber eliminado la etiqueta de cierre.

```js
assert.lengthOf(document.querySelectorAll('body'), 1);
```

Your `div` element should be nested in the `body`.

```js
assert.equal(document.querySelector('div')?.parentElement?.tagName, 'BODY');
```

Debes mover todos los demás elementos dentro del nuevo `div`.

```js
assert.lengthOf(document.querySelector('body > div#menu > main')?.children, 3);
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Cafe Menu</title>
    <link href="styles.css" rel="stylesheet"/>
  </head>
--fcc-editable-region--
  <body>
    <main>
      <h1>CAMPER CAFE</h1>
      <p>Est. 2020</p>
      <section>
        <h2>Coffee</h2>
      </section>
    </main>
  </body>
--fcc-editable-region--
</html>
```

```css
body {
  background-color: burlywood;
}

h1, h2, p {
  text-align: center;
}
```
