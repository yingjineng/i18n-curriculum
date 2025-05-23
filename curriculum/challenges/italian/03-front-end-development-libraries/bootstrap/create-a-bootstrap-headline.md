---
id: bad87fee1348bd9aec908846
title: Creare un titolo con Bootstrap
challengeType: 0
forumTopicId: 16812
dashedName: create-a-bootstrap-headline
---

# --description--

Now let's build something from scratch to practice our HTML, CSS and Bootstrap skills.

Costruiremo un "terreno di gioco" che presto useremo con le nostre sfide jQuery.

Per iniziare, crea un elemento `h3`, con il testo `jQuery Playground`.

Colora il tuo elemento `h3` con la classe Bootstrap `text-primary` e centralo con la classe `text-center` Bootstrap.

# --hints--

Dovresti aggiungere un elemento `h3` alla tua pagina.

```js
assert.lengthOf(document.querySelectorAll('h3'),1);
```

Il tuo elemento `h3` dovrebbe avere un tag di chiusura.

```js
assert.match(code,/<\/h3>/g);
assert.match(code,/<h3/g);
assert.equal( code.match(/<\/h3>/g).length , code.match(/<h3/g).length);
```

Il tuo elemento `h3` dovrebbe essere colorato applicando la classe `text-primary`

```js
assert.isTrue(document.querySelector('h3')?.classList?.contains('text-primary'));
```

Il tuo elemento `h3` dovrebbe essere centrato applicando la classe `text-center`

```js
assert.isTrue(document.querySelector('h3')?.classList?.contains('text-center'));
```

Il tuo elemento `h3` dovrebbe avere il testo `jQuery Playground`.

```js
assert.match(document.querySelector('h3')?.textContent, /jquery(\s)+playground/gi);
```

# --seed--

## --seed-contents--

```html

```

# --solutions--

```html
<h3 class="text-primary text-center">jQuery Playground</h3>
```
