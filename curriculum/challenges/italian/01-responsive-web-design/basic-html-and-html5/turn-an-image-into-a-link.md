---
id: bad87fee1348bd9aedf08820
title: Trasformare un'immagine in un collegamento
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cRdBnUr'
forumTopicId: 18327
dashedName: turn-an-image-into-a-link
---

# --description--

You can make elements into links by nesting them within an `a` element.

Metti la tua immagine all'interno di un elemento `a`. Ecco un esempio:

```html
<a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="Three kittens running towards the camera."></a>
```

Ricordati di usare `#` come proprietà `href` dei tuoi elementi `a` per trasformarli in link vuoti.

# --instructions--

Posiziona l'elemento immagine esistente all'interno di un elemento `a` (*anchor*).

Una volta fatto questo, passa sopra alla tua immagine con il cursore. Il puntatore normale del cursore dovrebbe diventare il puntatore di clic del collegamento. La foto è ora un collegamento.

# --hints--

L'elemento `img` esistente deve essere annidato all'interno di un elemento `a`.

```js
const anchor = document.querySelectorAll('a')[1];
const children = anchor.querySelectorAll("img");
assert.notEmpty(children);
```

Your `a` element should be a dead link with an `href` attribute set to `#`.

```js
const anchor = document.querySelectorAll('a')[1];
const parentHREF = anchor.querySelector("img").parentNode.getAttribute('href');
assert.match(parentHREF,new RegExp('#'));
```

Ognuno dei tuoi elementi `a` dovrebbe avere un tag di chiusura.

```js
assert.match(code,/<\/a>/g);
assert.match(code,/<a/g);
assert.strictEqual(code.match(/<\/a>/g).length, code.match(/<a/g).length)
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back.">

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```
