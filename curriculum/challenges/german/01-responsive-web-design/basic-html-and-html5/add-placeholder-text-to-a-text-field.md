---
id: bad87fee1348bd9aedf08830
title: Platzhaltertext zu einem Textfeld hinzufügen
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cKdJDhg'
forumTopicId: 16647
dashedName: add-placeholder-text-to-a-text-field
---

# --description--

Placeholder text is what is displayed in your `input` element before your user has inputted anything.

Du kannst Platzhaltertext wie folgt erstellen:

```html
<input type="text" placeholder="this is placeholder text">
```

**Note:** Remember that `input` is a void element.

# --instructions--

Setze den `placeholder`-Wert deines Text-`input` auf "cat photo URL".

# --hints--

Du solltest ein `placeholder`-Attribut zu dem bestehenden Text-`input`-Element hinzufügen.

```js
assert.notEmpty(document.querySelectorAll('input[placeholder]'));
```

Du solltest den Wert deines `placeholder`-Attributs auf `cat photo URL` setzen.

```js
assert.exists(document.querySelector('input'));
assert.exists(document.querySelector('input').getAttribute('placeholder'));
const placeholder = document.querySelector('input').getAttribute('placeholder');
assert.match(placeholder,/cat\s+photo\s+URL/gi);
```

Das fertige `input`-Element sollte kein schließendes Tag besitzen.

```js
assert.notMatch(code,/<input.*\/?>.*<\/input>/gi);
```

Das fertige `input`-Element sollte eine gültige Syntax enthalten.

```js
assert.notEmpty(document.querySelectorAll('input[type=text]'));
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
  <input type="text">
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
  <input type="text" placeholder="cat photo URL">
</main>
```
