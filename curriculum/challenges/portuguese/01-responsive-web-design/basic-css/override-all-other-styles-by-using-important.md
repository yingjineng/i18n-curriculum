---
id: bad87fee1348bd9aedf07756
title: Sobrescrever todos os outros estilos usando a palavra important
challengeType: 0
videoUrl: 'https://scrimba.com/c/cm24rcp'
forumTopicId: 18249
dashedName: override-all-other-styles-by-using-important
---

# --description--

Yay! We just proved that inline styles will override all the CSS declarations in your `style` element.

Mas veja bem. Existe mais uma forma de sobrescrever o CSS que declaramos anteriormente. Este é o método mais poderoso de todos. Mas antes de continuarmos, vamos falar sobre o motivo de você querer substituir o CSS.

Em muitas situações, você usará bibliotecas CSS. E elas podem, acidentalmente, substituir o CSS. Portanto, quando você precisar ter certeza absoluta de que um elemento deve possuir um CSS específico, poderá usar `!important`.

Vamos voltar à nossa classe `pink-text`. Lembre-se de que a classe `pink-text` foi sobrescrita por declarações de classe posteriores, declarações de id e estilos inline.

# --instructions--

Vamos adicionar a palavra-chave `!important` à declaração de estilo do elemento `h1` para ter 100% de certeza de que ele terá a cor de texto rosa.

Um exemplo de como fazer isso:

```css
color: red !important;
```

# --hints--

O elemento `h1` deve ter a classe `pink-text`.

```js
assert.isTrue(document.querySelector('h1').classList.contains('pink-text'));
```

O elemento `h1` deve ter a classe `blue-text`.

```js
assert.isTrue(document.querySelector('h1').classList.contains('blue-text'));
```

O elemento `h1` deve ter o `id` `orange-text`.

```js
assert.strictEqual(document.querySelector('h1').getAttribute('id'), 'orange-text');
```

O elemento `h1` deve ter o estilo inline `color: white`.

```js
const commentessCode = __helpers.removeHtmlComments(code);
assert.match(commentessCode, /<h1.*style/gi);
assert.match(commentessCode, /<h1.*style.*color\s*?:/gi);
```

A classe `pink-text` deve ter a palavra-chave `!important` para sobrescrever todas as outras declarações.

```js
assert.match(__helpers.removeCssComments(code), /\.pink-text\s*?\{[\s\S]*?color:.*pink.*!important\s*;?[^\.]*\}/g);
```

O elemento `h1` deve ser rosa.

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
  #orange-text {
    color: orange;
  }
  .pink-text {
    color: pink;
  }
  .blue-text {
    color: blue;
  }
</style>
<h1 id="orange-text" class="pink-text blue-text" style="color: white">Hello World!</h1>
```

# --solutions--

```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  #orange-text {
    color: orange;
  }
  .pink-text {
    color: pink !important;
  }
  .blue-text {
    color: blue;
  }
</style>
<h1 id="orange-text" class="pink-text blue-text" style="color: white">Hello World!</h1>
```
