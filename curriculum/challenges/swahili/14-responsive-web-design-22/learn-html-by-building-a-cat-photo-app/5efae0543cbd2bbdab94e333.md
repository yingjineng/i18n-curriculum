---
id: 5efae0543cbd2bbdab94e333
title: Step 32
challengeType: 0
dashedName: step-32
---

# --description--

To improve accessibility of the image you added, add an `alt` attribute with the text:

`Five cats looking around a field.`

# --hints--

Kipengele chako cha `figure` kinafaa kuwa na tagi ya kufungua. Tagi za ufunguzi zina sintaksia hii: `<elementName>`.

```js
assert(document.querySelectorAll('figure').length === 2);
```

Kipengele chako cha `figure` kinapaswa kuwa na tagi ya kufunga. Tagi za kufunga zina `/` mara baada ya herufi ya `<`.

```js
assert(code.match(/<\/figure>/g).length === 2);
```

Kunapaswa kuwa na kipengele cha `figure` juu ya tagi ya mwisho ya kufunga ya kipengele cha pili cha `section`.

```js
assert.strictEqual(document.querySelectorAll('main > section')?.[1]?.lastElementChild?.nodeName, 'FIGURE');
```

Kipengee cha Cats cha `img` kinapaswa kuwekwa katika kipengee cha `figure`.

```js
const catsImg = document.querySelectorAll('figure > img')[1];
assert.exists(catsImg);
```

The third image should have a `src` attribute set to `https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg`.

```js
const catsImg = document.querySelectorAll('figure > img')[1];
assert.strictEqual(
  catsImg?.src?.toLowerCase(), 'https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg'
);
```

Kipengele cha Cats cha `img` kinapaswa kuwa na sifa ya `alt` yenye thamani `Five cats looking around a field.`

```js
const catsImg = document.querySelectorAll('figure > img')[1];
assert.match(catsImg?.getAttribute('alt')?.replace(/\s+/g, ' '), /^Five cats looking around a field\.?$/i);
```

# --seed--

## --seed-contents--

```html
<html>
  <body>
    <main>
      <h1>CatPhotoApp</h1>
      <section>
        <h2>Cat Photos</h2>
        <p>Everyone loves <a href="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg">cute cats</a> online!</p>
        <p>See more <a target="_blank" href="https://freecatphotoapp.com">cat photos</a> in our gallery.</p>
        <a href="https://freecatphotoapp.com"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
      </section>
      <section>
        <h2>Cat Lists</h2>
        <h3>Things cats love:</h3>
        <ul>
          <li>catnip</li>
          <li>laser pointers</li>
          <li>lasagna</li>
        </ul>
        <figure>
          <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/lasagna.jpg" alt="A slice of lasagna on a plate.">
          <figcaption>Cats <em>love</em> lasagna.</figcaption>  
        </figure>
        <h3>Top 3 things cats hate:</h3>
        <ol>
          <li>flea treatment</li>
          <li>thunder</li>
          <li>other cats</li>
        </ol>
        <figure>
--fcc-editable-region--
          <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg">
--fcc-editable-region--
        </figure>
      </section>
    </main>
  </body>
</html>
```

