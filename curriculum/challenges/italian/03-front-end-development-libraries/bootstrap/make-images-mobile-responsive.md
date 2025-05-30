---
id: bad87fee1348bd9acde08812
title: Rendi le immagini responsive sui dispositivi mobili
challengeType: 0
forumTopicId: 18232
dashedName: make-images-mobile-responsive
---

# --description--

First, add a new image below the existing one. Set its `src` attribute to `https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg`.

Sarebbe bello se questa immagine potesse essere larga esattamente come lo schermo del nostro telefono.

Fortunatamente, con Bootstrap, tutto quello che dobbiamo fare è aggiungere la classe `img-responsive` alla tua immagine. Fai questo, e l'immagine dovrebbe adattarsi perfettamente alla larghezza della pagina.

# --hints--

Dovresti avere un totale di due immagini.

```js
assert.lengthOf(document.querySelectorAll('img'), 2);
```

La tua nuova immagine dovrebbe essere sotto la vecchia e avere la classe `img-responsive`.

```js
assert.isTrue(document.querySelectorAll('img')?.[1]?.classList?.contains('img-responsive'));
```

La tua nuova immagine non dovrebbe avere la classe `smaller-image`.

```js
assert.isFalse(document.querySelectorAll('img')?.[1]?.classList?.contains('smaller-image'));
```

La tua nuova immagine dovrebbe avere un attributo `src` di `https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg`.

```js
assert.equal(document.querySelectorAll('img')?.[1]?.getAttribute('src') , 'https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg');
```

Il tuo nuovo elemento `img` dovrebbe avere una parentesi angolare di chiusura.

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
