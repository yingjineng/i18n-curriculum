---
id: bad87fee1348bd9acde08812
title: Haz imágenes adaptables a dispositivos móviles
challengeType: 0
forumTopicId: 18232
dashedName: make-images-mobile-responsive
---

# --description--

Primero, agrega una nueva imagen debajo de la existente. Establece su atributo `src` a `https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg`.

Seria genial si esta imagen pudiera tener exactamente el ancho de la pantalla de nuestro teléfono.

Afortunadamente, con Bootstrap, todo lo que necesitamos hacer es agregar la clase `img-responsive` a nuestra imagen. Hazlo, y la imagen debería caber perfectamente en el ancho de tu página.

# --hints--

Debes tener un total de dos imágenes.

```js
assert.lengthOf(document.querySelectorAll('img'), 2);
```

Tu nueva imagen debe estar debajo de la anterior y tener la clase `img-responsive`.

```js
assert.isTrue(document.querySelectorAll('img')?.[1]?.classList?.contains('img-responsive'));
```

Tu nueva imagen no debe tener la clase `smaller-image`.

```js
assert.isFalse(document.querySelectorAll('img')?.[1]?.classList?.contains('smaller-image'));
```

Tu nueva imagen debe tener el atributo `src` con el valor `https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg`.

```js
assert.equal(document.querySelectorAll('img')?.[1]?.getAttribute('src') , 'https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg');
```

Tu nuevo elemento `img` debe tener etiqueta de cierre.

```js
assert.match(code,/<img/g);
assert.lengthOf(code.match(/<img[^<]*>/g), 2);
assert.lengthOf(code.match(/<img/g), 2);
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
  <h2 class="red-text">CatPhotoApp</h2>

  <p>Click here for <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

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
  <h2 class="red-text">CatPhotoApp</h2>

  <p>Click here for <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive">

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
