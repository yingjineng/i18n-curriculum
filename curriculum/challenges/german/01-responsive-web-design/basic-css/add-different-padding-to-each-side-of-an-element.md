---
id: bad87fee1348bd9aedf08824
title: Füge jeder Seite eines Elements einen andere Innenabstand hinzu
challengeType: 0
videoUrl: 'https://scrimba.com/c/cB7mwUw'
forumTopicId: 16634
dashedName: add-different-padding-to-each-side-of-an-element
---

# --description--

Sometimes you will want to customize an element so that it has different amounts of `padding` on each of its sides.

CSS erlaubt es, das `padding` mit folgenden Eigenschaften für jede Seite individuell festzulegen: `padding-top`, `padding-right`, `padding-bottom` und `padding-left`.

# --instructions--

Gib der blauen Box ein `padding` von `40px` oben und links, aber nur `20px` auf der unteren und rechten Seite.

# --hints--

Deine `blue-box` Klasse sollte der oberen Seite der Elemente `40px` `padding` zuweisen.

```js
const blueBox = document.querySelector('.blue-box');
const paddingTop = window.getComputedStyle(blueBox)['padding-top'];
assert.strictEqual(paddingTop, '40px');
```

Deine `blue-box` Klasse sollte der rechten Seite der Elemente `20px` `padding` zuweisen.

```js
const blueBox = document.querySelector('.blue-box');
const paddingRight = window.getComputedStyle(blueBox)['padding-right'];
assert.strictEqual(paddingRight, '20px');
```

Deine `blue-box` Klasse sollte der unteren Seite der Elemente `20px` `padding` zuweisen.

```js
const blueBox = document.querySelector('.blue-box');
const paddingBottom = window.getComputedStyle(blueBox)['padding-bottom'];
assert.strictEqual(paddingBottom, '20px');
```

Deine `blue-box` Klasse sollte der linken Seite der Elemente `40px` `padding` zuweisen.

```js
const blueBox = document.querySelector('.blue-box');
const paddingLeft = window.getComputedStyle(blueBox)['padding-left'];
assert.strictEqual(paddingLeft, '40px');
```

# --seed--

## --seed-contents--

```html
<style>
  .injected-text {
    margin-bottom: -25px;
    text-align: center;
  }

  .box {
    border-style: solid;
    border-color: black;
    border-width: 5px;
    text-align: center;
  }

  .yellow-box {
    background-color: yellow;
    padding: 10px;
  }

  .red-box {
    background-color: crimson;
    color: #fff;
    padding-top: 40px;
    padding-right: 20px;
    padding-bottom: 20px;
    padding-left: 40px;
  }

  .blue-box {
    background-color: blue;
    color: #fff;
  }
</style>
<h5 class="injected-text">margin</h5>

<div class="box yellow-box">
  <h5 class="box red-box">padding</h5>
  <h5 class="box blue-box">padding</h5>
</div>
```

# --solutions--

```html
<style>
  .injected-text {
    margin-bottom: -25px;
    text-align: center;
  }

  .box {
    border-style: solid;
    border-color: black;
    border-width: 5px;
    text-align: center;
  }

  .yellow-box {
    background-color: yellow;
    padding: 10px;
  }

  .red-box {
    background-color: crimson;
    color: #fff;
    padding-top: 40px;
    padding-right: 20px;
    padding-bottom: 20px;
    padding-left: 40px;
  }

  .blue-box {
    background-color: blue;
    color: #fff;
    padding-top: 40px;
    padding-right: 20px;
    padding-bottom: 20px;
    padding-left: 40px;
  }
</style>
<h5 class="injected-text">margin</h5>

<div class="box yellow-box">
  <h5 class="box red-box">padding</h5>
  <h5 class="box blue-box">padding</h5>
</div>
```
