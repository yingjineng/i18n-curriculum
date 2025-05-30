---
id: bad87fee1348bd9aedf08756
title: Dare una priorità maggiore a uno stile rispetto a un altro
challengeType: 0
videoUrl: 'https://scrimba.com/c/cZ8wnHv'
forumTopicId: 18258
dashedName: prioritize-one-style-over-another
---

# --description--

Sometimes your HTML elements will receive multiple styles that conflict with one another.

Ad esempio, l'elemento `h1` non può essere sia verde che rosa allo stesso tempo.

Vediamo cosa succede quando creiamo una classe che rende il testo rosa, quindi applicalo a un elemento. La nostra classe *sovrascriverà* la proprietà CSS `color: green;` dell'elemento `body`?

# --instructions--

Crea una classe CSS chiamata `pink-text` che dia a un elemento il colore rosa.

Dai al tuo elemento `h1` la classe `pink-text`.

# --hints--

L'elemento `h1` dovrebbe avere la classe `pink-text`.

```js
assert.isTrue(document.querySelector('h1').classList.contains('pink-text'));
```

Il tuo `<style>` dovrebbe avere una classe CSS `pink-text` che modifica il `color`.

```js
assert.match(__helpers.removeCssComments(code), /\.pink-text\s*\{\s*color\s*:\s*.+\s*;?\s*\}/g);
```

Il tuo elemento `h1` dovrebbe essere rosa.

```js
const h1Element = document.querySelector('h1');
const color = window.getComputedStyle(h1Element)['color']; 
assert.strictEqual(color, 'rgb(255, 192, 203)');
```

# --seed--

## --seed-contents--

```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
</style>
<h1>Hello World!</h1>
```

# --solutions--

```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  .pink-text {
    color: pink;
  }
</style>
<h1 class="pink-text">Hello World!</h1>
```
