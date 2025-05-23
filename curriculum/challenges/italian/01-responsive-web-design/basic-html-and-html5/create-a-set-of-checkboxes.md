---
id: bad87fee1348bd9aedf08835
title: Creare un gruppo di caselle di spunta
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cqrkJsp'
forumTopicId: 16821
dashedName: create-a-set-of-checkboxes
---

# --description--

Forms commonly use <dfn>checkboxes</dfn> for questions that may have more than one answer.

Le caselle di spunta sono un tipo di `input`.

Ognuna delle tue caselle di spunta può essere annidata all'interno del suo elemento `label`. L'inserimento di un elemento `input` all'interno di un elemento `label` associerà automaticamente l'input della casella di spunta all'elemento label che lo circonda.

Tutti i gli input relativi alla casella di spunta dovrebbero avere lo stesso attributo `name`.

È una buona pratica definire esplicitamente la relazione tra un `input` di tipo checkbox e la relativa `label` impostando l'attributo `for` sulla `label` in modo che corrisponda all'attributo `id` dell'elemento `input` associato.

Ecco un esempio di casella di spunta:

```html
<label for="loving"><input id="loving" type="checkbox" name="personality"> Loving</label>
```

# --instructions--

Aggiungi al tuo modulo tre caselle di spunta. Ogni casella di spunta dovrebbe essere annidata all'interno del proprio elemento `label`. Tutti e tre dovrebbero condividere l'attributo `name` di `personality`.

# --hints--

La tua pagina dovrebbe avere tre caselle di spunta.

```js
assert.lengthOf(document.querySelectorAll('input[type="checkbox"]'),3);
```

Ogni casella di spunta dovrebbe essere annidata all'interno del proprio elemento `label`.

```js
assert.lengthOf(document.querySelectorAll('label > input[type="checkbox"]:only-child'),3);
```

Assicurati che ciascuno dei tuoi elementi `label` abbia un tag di chiusura.

```js
assert.match(code,/<\/label>/g);
assert.match(code,/<label/g);
assert.strictEqual(code.match(/<\/label>/g).length,code.match(/<label/g).length)
```

Alle tue caselle di spunta dovrebbe essere dato l'attributo `name` di `personality`.

```js
assert.lengthOf([...document.querySelectorAll('label > input[type="checkbox"]')].filter(x => x.name === "personality"),3);
```

Ognuna delle tue caselle di spunta dovrebbe essere inserita all'interno del tag `form`.

```js
assert.strictEqual(document.querySelector('label').parentNode.tagName,'FORM');
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
  <form action="https://www.freecatphotoapp.com/submit-cat-photo">
    <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor"> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
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
    <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor"> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <label for="playful"><input id="playful" type="checkbox" name="personality">Playful</label>
    <label for="lazy"><input id="lazy" type="checkbox" 
name="personality">Lazy</label>
    <label for="evil"><input id="evil" type="checkbox" 
name="personality">Evil</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
