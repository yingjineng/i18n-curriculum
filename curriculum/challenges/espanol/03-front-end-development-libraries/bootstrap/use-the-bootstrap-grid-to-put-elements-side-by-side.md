---
id: bad88fee1348ce8acef08815
title: Usa la Cuadrilla de Bootstrap para Colocar Elementos Uno al Lado del Otro
challengeType: 0
forumTopicId: 18371
dashedName: use-the-bootstrap-grid-to-put-elements-side-by-side
---

# --description--

Bootstrap utiliza un sistema adaptable de cuadrilla de 12 columnas, el cual hace que sea fácil poner elementos en dos filas y especificar la anchura relativa de cada elemento. La mayoría de las clases de Bootstrap pueden ser aplicadas al elemento `div`.

Bootstrap tiene diferentes atributos de ancho de columna que usa dependiendo cuan ancha es la pantalla del usuario. Por ejemplo, los teléfonos tienen pantallas más angostas y las laptops tienen pantallas más anchas.

Tomemos por ejemplo la clase de Bootstrap `col-md-*`. Aquí, `md` significa mediano, y `*` es un número especificando cuantas columnas de ancho debería ocupar el elemento. En este caso, el ancho de columna de un elemento en una pantalla de tamaño mediano, como una laptop, está siendo especificado.

En el 'Cat Photo App' que estamos creando, vamos a usar `col-xs-*`, donde `xs` significa extra pequeño ("extra small" como una pantalla de teléfono), y `*` es el número de columnas que va a tomar el elemento en anchura.

Pon los botones `Like`, `Info` y `Delete` lado a lado, anidando los tres dentro de un elemento `<div class="row">`, luego, cada uno de ellos dentro de un elemento `<div class="col-xs-4">`.

La clase `row` es aplicada a un `div`, y los botones mismos pueden ser anidados dentro de él.

# --hints--

Todos tus botones deben estar anidados dentro del mismo elemento `div` con la clase `row`.

```js
const row = document.querySelector('div.row');
const rowChildren = row?.querySelectorAll(`:scope ${'button'}`); 
assert.lengthOf(rowChildren, 3);
```

Cada uno de tus botones de Bootstrap deben estar anidados dentro de su propio elemento `div` con la clase `col-xs-4`.

```js
const columns = document.querySelectorAll('div.col-xs-4');

const firstButton = columns?.[0]?.querySelectorAll(`:scope ${'button'}`)
assert.lengthOf(firstButton,1);

const secondButton = columns?.[1]?.querySelectorAll(`:scope ${'button'}`)
assert.lengthOf(secondButton,1);

const thirdButton = columns?.[2]?.querySelectorAll(`:scope ${'button'}`)
assert.lengthOf(thirdButton,1);

```

Cada uno de tus elementos `button` deben tener una etiqueta de cierre.

```js
assert.match(code,/<\/button>/g);
assert.match(code,/<button/g);
assert.equal(code.match(/<\/button>/g).length , code.match(/<button/g).length);
```

Cada uno de tus elementos `div` deben tener una etiqueta de cierre.

```js
assert.match(code,/<\/div>/g);
assert.match(code,/<div/g);
assert.equal(code.match(/<\/div>/g).length , code.match(/<div/g).length);
```

# --seed--

## --seed-contents--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }

  .smaller-image {
    width: 100px;
  }
</style>

<div class="container-fluid">
  <h2 class="red-text text-center">CatPhotoApp</h2>

  <p>Click here for <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <button class="btn btn-block btn-primary">Like</button>
  <button class="btn btn-block btn-info">Info</button>
  <button class="btn btn-block btn-danger">Delete</button>
  <p>Things cats love:</p>
  <ul>
    <li>catnip</li>
    <li>laser pointers</li>
    <li>lasagna</li>
  </ul>
  <p>Top 3 things cats hate:</p>
  <ol>
    <li>flea treatment</li>
    <li>thunder</li>
    <li>other cats</li>
  </ol>
  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
    <label><input type="checkbox" name="personality"> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Crazy</label>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</div>
```

# --solutions--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }

  .smaller-image {
    width: 100px;
  }
</style>

<div class="container-fluid">
  <h2 class="red-text text-center">CatPhotoApp</h2>

  <p>Click here for <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <div class="row">
    <div class="col-xs-4">
      <button class="btn btn-block btn-primary">Like</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-info">Info</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-danger">Delete</button>
    </div>
  </div>

  <p>Things cats love:</p>
  <ul>
    <li>catnip</li>
    <li>laser pointers</li>
    <li>lasagna</li>
  </ul>
  <p>Top 3 things cats hate:</p>
  <ol>
    <li>flea treatment</li>
    <li>thunder</li>
    <li>other cats</li>
  </ol>
  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
    <label><input type="checkbox" name="personality"> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Crazy</label>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</div>
```
