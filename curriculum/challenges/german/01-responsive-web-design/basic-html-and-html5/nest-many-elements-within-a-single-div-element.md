---
id: bad87fee1348bd9aede08835
title: Verschachteln vieler Elemente innerhalb eines einzelnen div-Elements
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cNW4kC3'
forumTopicId: 18246
dashedName: nest-many-elements-within-a-single-div-element
---

# --description--

The `div` element, also known as a division element, is a general purpose container for other elements.

Das `div`-Element ist wahrscheinlich das am häufigsten verwendete HTML-Element von allen.

Genau wie jedes andere nicht selbstschließende Element kannst du ein `div`-Element mit `<div>` öffnen und es in einer anderen Zeile mit `</div>` schließen.

# --instructions--

Platziere deine Listen "Dinge, die Katzen lieben" und "Top 3 Dinge, die Katzen hassen" innerhalb eines einzigen `div`-Elements.

Tipp: Versuche dein öffnendes `div`-Tag über dein `p`-Element "Dinge, die Katzen lieben" und dein schließendes `div`-Tag nach deinem schließenden `ol`-Tag zu platzieren, so dass beide deiner Listen innerhalb eines `div` stehen.

# --hints--

Dein `p`-Element sollte in deinem `div`-Element eingebettet sein.

```js
const div = document.querySelector('div');
const children = div.querySelectorAll('p');
assert.isAbove(children.length,1);
```

Dein `ul`-Element sollte in deinem `div`-Element eingebettet sein.

```js
const div = document.querySelector('div');
const children = div.querySelectorAll('ul');
assert.notEmpty(children);
```

Dein `ol`-Element sollte in deinem `div`-Element eingebettet sein.

```js
const div = document.querySelector('div');
const children = div.querySelectorAll('ol');
assert.notEmpty(children);
```

Dein `div`-Element sollte einen schließenden Tag haben.

```js
assert.match(code,/<\/div>/g);
assert.strictEqual(code.match(/<\/div>/g).length,code.match(/<div>/g).length);
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
    <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor" value="indoor" checked> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor" value="outdoor"> Outdoor</label><br>
    <label for="loving"><input id="loving" type="checkbox" name="personality" value="loving" checked> Loving</label>
    <label for="lazy"><input id="lazy" type="checkbox" name="personality" value="lazy"> Lazy</label>
    <label for="energetic"><input id="energetic" type="checkbox" name="personality" value="energetic"> Energetic</label><br>
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
  <div>
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
  </div>
  <form action="https://www.freecatphotoapp.com/submit-cat-photo">
    <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor" value="indoor" checked> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor" value="outdoor"> Outdoor</label><br>
    <label for="loving"><input id="loving" type="checkbox" name="personality" value="loving" checked> Loving</label>
    <label for="lazy"><input id="lazy" type="checkbox" name="personality" value="lazy"> Lazy</label>
    <label for="energetic"><input id="energetic" type="checkbox" name="personality" value="energetic"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
