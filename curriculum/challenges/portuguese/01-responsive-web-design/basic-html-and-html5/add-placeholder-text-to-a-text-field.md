---
id: bad87fee1348bd9aedf08830
title: Adicionar texto placeholder a um campo de texto
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cKdJDhg'
forumTopicId: 16647
dashedName: add-placeholder-text-to-a-text-field
---

# --description--

Placeholder text is what is displayed in your `input` element before your user has inputted anything.

Você pode criar um texto placeholder da seguinte maneira:

```html
<input type="text" placeholder="this is placeholder text">
```

**Note:** Remember that `input` is a void element.

# --instructions--

Defina o valor do `placeholder` do elemento `input` de texto para "cat photo URL".

# --hints--

Você deve adicionar um atributo `placeholder` ao elemento `input` de texto que já existe.

```js
assert.notEmpty(document.querySelectorAll('input[placeholder]'));
```

Você deve definir o valor do atributo `placeholder` para `cat photo URL`.

```js
assert.exists(document.querySelector('input'));
assert.exists(document.querySelector('input').getAttribute('placeholder'));
const placeholder = document.querySelector('input').getAttribute('placeholder');
assert.match(placeholder,/cat\s+photo\s+URL/gi);
```

O elemento `input` final não deve ter uma tag de fechamento.

```js
assert.notMatch(code,/<input.*\/?>.*<\/input>/gi);
```

O elemento `input` final deve ter uma sintaxe válida.

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
