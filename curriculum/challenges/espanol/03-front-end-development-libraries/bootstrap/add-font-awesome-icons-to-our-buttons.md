---
id: bad87fee1348bd9aedd08845
title: Agrega iconos Font Awesome a nuestros botones
challengeType: 0
forumTopicId: 16638
required:
  - 
    link: 'https://use.fontawesome.com/releases/v5.8.1/css/all.css'
    raw: true
dashedName: add-font-awesome-icons-to-our-buttons
---

# --description--

Font Awesome es una conveniente librería de iconos. Estos íconos pueden ser fuentes web o gráficos vectoriales. Estos íconos son tratados como fuentes. Puedes especificar su tamaño usando píxeles, y ellos asumirán el tamaño de fuente de su elemento HTML padre.

Puedes incluir Font Awesome en cualquier aplicación agregando el siguiente código al principio de tu HTML:

```html
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.1/css/all.css" integrity="sha384-50oBUHEmvpQ+1lW4y57PTFmhCaXp0ML5d60M1M7uH2+nqUivzIebhndOJK28anvf" crossorigin="anonymous">
```

En este caso, ya lo hemos añadido por ti en esta página tras bambalinas.

El elemento `i` fue originalmente usado para crear elementos itálicos, pero ahora es comúnmente usado para iconos. Puedes añadir las clases de Font Awesome al elemento `i` para convertirlo en un icono, por ejemplo:

```html
<i class="fas fa-info-circle"></i>
```

Ten en cuenta que el elemento `span` también es aceptable para usar con iconos.

# --instructions--

Usa Font Awesome para añadir un icono `thumbs-up` a tu botón de "Like", dándole un elemento `i` con las clases `fas` y `fa-thumbs-up`. Asegúrate de dejar el texto `Like` junto al icono.

# --hints--

Debes añadir un elemento `i` con las clases `fas` y `fa-thumbs-up`.

```js
assert.isTrue(document.querySelector('i')?.classList?.value === 'fas fa-thumbs-up' || document.querySelector('span')?.classList?.value === 'fas fa-thumbs-up');
```

Tu icono `fa-thumbs-up` debe estar ubicado dentro del botón "Like".

```js
const iconTextContent = document.querySelector('i.fa-thumbs-up')?.parentNode?.textContent;  
const spanTextContent = document.querySelector('span.fa-thumbs-up')?.parentNode?.textContent;  
assert.isTrue(
  (iconTextContent?.match(/Like/gi) &&
    document.querySelector('.btn-primary > i') === document.querySelector('.fas.fa-thumbs-up')) ||
    (spanTextContent?.match(/Like/gi) &&
      document.querySelector('.btn-primary > span') === document.querySelector('.fas.fa-thumbs-up')));
```

Tu elemento `i` debe estar anidado dentro de tu elemento `button`.

```js
const button = document.querySelector('button'); 
const i = button?.querySelectorAll("i");
const span =  button?.querySelectorAll("span");
assert(i.length > 0 ||span.length > 0);
```

Tu elemento icono debe tener una etiqueta de cierre.

```js
assert.match(code, /(<\/i>|<\/span>)\s*Like\s*<\/button>/g);
```

# --seed--

## --seed-contents--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  h2 {
    font-family: Lobster, Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }
</style>

<div class="container-fluid">
  <div class="row">
    <div class="col-xs-8">
      <h2 class="text-primary text-center">CatPhotoApp</h2>
    </div>
    <div class="col-xs-4">
      <a href="#"><img class="img-responsive thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
    </div>
  </div>
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
  <p>Things cats <span class="text-danger">love:</span></p>
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
  h2 {
    font-family: Lobster, Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }
</style>

<div class="container-fluid">
  <div class="row">
    <div class="col-xs-8">
      <h2 class="text-primary text-center">CatPhotoApp</h2>
    </div>
    <div class="col-xs-4">
      <a href="#"><img class="img-responsive thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
    </div>
  </div>
  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <div class="row">
    <div class="col-xs-4">
      <button class="btn btn-block btn-primary"><i class="fas fa-thumbs-up"></i> Like</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-info">Info</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-danger">Delete</button>
    </div>
  </div>
  <p>Things cats <span class="text-danger">love:</span></p>
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
