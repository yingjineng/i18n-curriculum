---
id: bad87fee1348bd9aedf08835
title: Eine Gruppe (Set) von Checkboxen erstellen
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cqrkJsp'
forumTopicId: 16821
dashedName: create-a-set-of-checkboxes
---

# --description--

Forms commonly use <dfn>checkboxes</dfn> for questions that may have more than one answer.

Checkboxen sind ein Typ von `input`.

Jede deiner Checkboxen kann in einem eigenen `label`-Element verschachtelt werden. Indem ein `input`-Element in ein `label`-Element eingeschlossen wird, wird die Eingabe in die Checkbox automatisch mit dem sie umgebenden Label-Element verknüpft.

Alle zusammengehörigen Checkboxeingaben sollten das gleiche `name`-Attribut besitzen.

Es gilt als bewährte Praxis, die Beziehung zwischen einer Checkbox `input` und dem zugehörigen `label` explizit zu definieren, indem das `for`-Attribut des `label`-Elements auf das `id`-Attribut des zugehörigen `input`-Elements gesetzt wird.

Hier ist ein Beispiel für eine Checkbox:

```html
<label for="loving"><input id="loving" type="checkbox" name="personality"> Loving</label>
```

# --instructions--

Füge deinem Formular eine Gruppe von drei Checkboxen hinzu. Jede Checkbox sollte in einem eigenen `label`-Element eingebettet sein. Alle drei sollten das `name`-Attribut `personality` verwenden.

# --hints--

Deine Seite sollte drei Checkbox-Elemente enthalten.

```js
assert.lengthOf(document.querySelectorAll('input[type="checkbox"]'),3);
```

Jedes deiner drei Checkbox-Elemente sollte in seinem eigenen `label`-Element eingebettet sein.

```js
assert.lengthOf(document.querySelectorAll('label > input[type="checkbox"]:only-child'),3);
```

Stelle sicher, dass jedes deiner `label`-Elemente einen schließenden Tag besitzt.

```js
assert.match(code,/<\/label>/g);
assert.match(code,/<label/g);
assert.strictEqual(code.match(/<\/label>/g).length,code.match(/<label/g).length)
```

Deine Checkboxen sollten das `name`-Attribut `personality` erhalten.

```js
assert.lengthOf([...document.querySelectorAll('label > input[type="checkbox"]')].filter(x => x.name === "personality"),3);
```

Jede deiner Checkboxen sollte innerhalb des `form`-Tags hinzugefügt werden.

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
