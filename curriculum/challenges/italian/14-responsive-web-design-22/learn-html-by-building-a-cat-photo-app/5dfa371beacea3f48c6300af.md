---
id: 5dfa371beacea3f48c6300af
title: Step 21
challengeType: 0
dashedName: step-21
---

# --description--

When you add a lower rank heading element to the page, it's implied that you're starting a new subsection.

Dopo l'ultimo elemento `h2` del secondo elemento `section`, aggiungi un elemento `h3` con il testo:

`Things cats love:`

# --hints--

Il secondo elemento `section` è mancante o non ha entrambi i tag di apertura e di chiusura.

```js
assert(
  document.querySelectorAll('main > section')[1] &&
    code.match(/\<\/section>/g).length == 2
);
```

Ci dovrebbe essere un elemento `h3` proprio sopra il tag di chiusura del secondo elemento `section`.

```js
assert(
  document.querySelectorAll('main > section')[1].lastElementChild.nodeName ===
    'H3'
);
```

Your `h3` element should have a closing tag. Closing tags have a `/` just after the `<` character.

```js
assert.lengthOf(code.match(/<\/h3>/g), 1);
```

L'elemento `h3` al di sopra del tag di chiusura dell'elemento `section` dovrebbe contenere il testo `Things cats love:`. Assicurati di includere i due punti alla fine del testo.

```js
assert(
  document
    .querySelectorAll('main > section')[1]
    .lastElementChild.innerText.toLowerCase()
    .replace(/\s+/g, ' ') === 'things cats love:'
);
```

Ci dovrebbe essere un elemento `h2` con il testo `Cat Lists` sopra l'ultimo elemento `h3` che è annidato nell'ultimo elemento `section`. Potresti aver accidentalmente eliminato l'elemento `h2`.

```js
const secondSectionLastElemNode = document.querySelectorAll('main > section')[1]
  .lastElementChild;
assert(
  secondSectionLastElemNode.nodeName === 'H3' &&
    secondSectionLastElemNode.previousElementSibling.innerText
      .toLowerCase()
      .replace(/\s+/g, ' ') === 'cat lists'
);
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
--fcc-editable-region--
      <section>
        <h2>Cat Lists</h2>

      </section>
--fcc-editable-region--
    </main>
  </body>
</html>
```

