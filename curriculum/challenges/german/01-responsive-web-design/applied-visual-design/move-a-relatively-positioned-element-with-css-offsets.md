---
id: 587d781e367417b2b2512aca
title: Versetze ein relativ positioniertes Element mit CSS-Offsets
challengeType: 0
videoUrl: 'https://scrimba.com/c/c9bQEA4'
forumTopicId: 301065
dashedName: move-a-relatively-positioned-element-with-css-offsets
---

# --description--

The CSS offsets of `top` or `bottom`, and `left` or `right` tell the browser how far to offset an item relative to where it would sit in the normal flow of the document. You're offsetting an element away from a given spot, which moves the element away from the referenced side (effectively, the opposite direction). As you saw in the last challenge, using the `top` offset moved the `h2` downwards. Likewise, using a `left` offset moves an item to the right.

# --instructions--

Verwende Offsets, um die `h2` um 15 Pixel nach rechts und 10 Pixel nach oben zu bewegen.

# --hints--

Dein Code sollte Offsets verwenden, um die `h2` 10px relativ nach oben zu versetzen. Anders ausgedrückt, setze es 10px von `bottom` ab, wo es sich normalerweise befindet.

```js
const h2Element =document.querySelector('h2')
const h2Style = window.getComputedStyle(h2Element);
assert.equal(h2Style?.bottom, '10px');
```

Dein Code sollte Offsets verwenden, um die `h2` 15px relativ nach rechts zu versetzen. Anders ausgedrückt, setze es 15px von `left` ab, wo es sich normalerweise befindet.

```js
const h2Element =document.querySelector('h2')
const h2Style = window.getComputedStyle(h2Element);
assert.equal(h2Style?.left , '15px');
```

# --seed--

## --seed-contents--

```html
<head>
<style>
  h2 {
    position: relative;


  }
</style>
</head>
<body>
  <h1>On Being Well-Positioned</h1>
  <h2>Move me!</h2>
  <p>I still think the h2 is where it normally sits.</p>
</body>
```

# --solutions--

```html
<head>
<style>
  h2 {
    position: relative;
    left: 15px;
    bottom: 10px;
  }
</style>
</head>
<body>
  <h1>On Being Well-Positioned</h1>
  <h2>Move me!</h2>
  <p>I still think the h2 is where it normally sits.</p>
</body>
```
