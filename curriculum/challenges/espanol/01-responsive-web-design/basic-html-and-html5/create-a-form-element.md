---
id: bad87fee1348bd9aede08830
title: Crea un elemento de formulario
challengeType: 0
forumTopicId: 16817
dashedName: create-a-form-element
---

# --description--

Puedes construir formularios web que realmente envíen datos a un servidor usando sólo HTML puro. Puedes hacer esto especificando un atributo `action` en tu elemento `form`.

Por ejemplo:

```html
<form action="url-where-you-want-to-submit-form-data">
  <input>
</form>
```

# --instructions--

Anida el elemento `input` existente dentro de un elemento `form` y asigna `"https://www.freecatphotoapp.com/submit-cat-photo"` al atributo `action` del elemento `form`.

# --hints--

El elemento `input` existente debe anidarse dentro de un elemento `form`.

```js
const inputElem = document.querySelector('form input');
assert.strictEqual(inputElem.getAttribute('type'),'text'); 
assert.strictEqual(inputElem.getAttribute('placeholder'),'cat photo URL');
```

Tu formulario `form` debe tener un atributo `action` que esté establecido como `https://www.freecatphotoapp.com/submit-cat-photo`.

```js
const action = document.querySelector('form').getAttribute('action');
assert.match(action,/^https:\/\/(www\.)?freecatphotoapp\.com\/submit-cat-photo$/i);
```

Tu elemento `form` debe tener etiquetas correctamente abiertas y cerradas.

```js
assert.match(code,/<\/form>/g);
assert.match(code,/<form [^<]*>/g);
assert.strictEqual(code.match(/<\/form>/g).length,code.match(/<form [^<]*>/g).length);
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

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
  <input type="text" placeholder="cat photo URL">
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

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
  <form action="https://www.freecatphotoapp.com/submit-cat-photo">
    <input type="text" placeholder="cat photo URL">
  </form>
</main>
```
