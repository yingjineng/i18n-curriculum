---
id: 5dfa371beacea3f48c6300af
title: Step 21
challengeType: 0
dashedName: step-21
---

# --description--

When you add a lower rank heading element to the page, it's implied that you're starting a new subsection.

Depois do último elemento `h2` do segundo elemento `section`, adicione um elemento `h3` com este texto:

`Things cats love:`

# --hints--

O segundo elemento `section` parece não ter a tag de abertura, a de fechamento ou as duas tags.

```js
assert(
  document.querySelectorAll('main > section')[1] &&
    code.match(/\<\/section>/g).length == 2
);
```

O elemento `h3` deve estar logo acima da tag de fechamento de fechamento do segundo elemento `section`.

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

O elemento `h3` logo acima da tag de fechamento do segundo elemento `section` deve ter o texto `Things cats love:`. Certifique-se de incluir os dois pontos ao final do texto.

```js
assert(
  document
    .querySelectorAll('main > section')[1]
    .lastElementChild.innerText.toLowerCase()
    .replace(/\s+/g, ' ') === 'things cats love:'
);
```

Deve haver um elemento `h2` com o texto `Cat Lists` acima do último elemento `h3` que está aninhado no último elemento `section`. Você pode ter excluído o elemento `h2` acidentalmente.

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

