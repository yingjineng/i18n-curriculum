---
id: bad87fee1348bd9aedf08828
title: Criar uma lista ordenada
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cQ3B8TM'
forumTopicId: 16824
dashedName: create-an-ordered-list
---

# --description--

HTML has another special element for creating <dfn>ordered lists</dfn>, or numbered lists.

Listas ordenadas têm um elemento `<ol>` inicial, seguido por uma quantidade qualquer de elementos `<li>`. Por fim, listas ordenadas são fechadas com uma tag `</ol>`.

Por exemplo:

```html
<ol>
  <li>Garfield</li>
  <li>Sylvester</li>
</ol>
```

criaria uma lista numerada com `Garfield` e `Sylvester`.

# --instructions--

Crie uma lista ordenada com as três coisas que os gatos mais odeiam.

# --hints--

Você deve ter uma lista ordenada para as `Top 3 things cats hate:`

```js
const previousElement = document.querySelector('ol').previousElementSibling; 
assert.match(previousElement.textContent,/Top 3 things cats hate:/i);
```

Você deve ter uma lista não ordenada para `Things cats love:`

```js
const previousElement = document.querySelector('ul').previousElementSibling; 
assert.match(previousElement.textContent,/Things cats love:/i);
```

Você deve ter apenas um elemento `ul`.

```js
assert.lengthOf(document.querySelectorAll('ul'), 1);
```

Você deve ter apenas um elemento `ol`.

```js
assert.lengthOf(document.querySelectorAll('ol'), 1);
```

Você precisa de três elementos `li` dentro do elemento `ul`.

```js
assert.lengthOf(document.querySelectorAll('ul li'), 3);
```

Você precisa de três elementos `li` dentro do elemento `ol`.

```js
assert.lengthOf(document.querySelectorAll('ol li'), 3);
```

O elemento `ul` deve ter uma tag de fechamento.

```js
assert.match(code,/<\/ul>/g);
assert.strictEqual(code.match(/<\/ul>/g).length ,code.match(/<ul>/g).length);
```

O elemento `ol` deve ter uma tag de fechamento.

```js
assert.match(code,/<\/ol>/g);
assert.strictEqual(code.match(/<\/ol>/g).length ,code.match(/<ol>/g).length);
```

O elemento `li` deve ter uma tag de fechamento.

```js
assert.match(code,/<\/li>/g);
assert.match(code,/<li>/g);
assert.strictEqual(code.match(/<\/li>/g).length ,code.match(/<li>/g).length);
```

Os elementos `li` da lista não ordenada não devem estar vazios.

```js
[...document.querySelectorAll('ul li')].forEach((val) =>
  assert.isNotEmpty(__helpers.removeWhiteSpace(val.textContent))
);
```

Os elementos `li` da lista ordenada não devem estar vazios.

```js
[...document.querySelectorAll('ol li')].forEach((val) =>
  assert.isNotEmpty(__helpers.removeWhiteSpace(val.textContent))
);
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
    <li>hate 1</li>
    <li>hate 2</li>
    <li>hate 3</li>
  </ol>
</main>
```
