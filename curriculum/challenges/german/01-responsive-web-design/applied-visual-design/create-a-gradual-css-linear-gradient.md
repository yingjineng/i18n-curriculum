---
id: 587d78a5367417b2b2512ad6
title: Erstellen eines linearen CSS-Farbverlaufs
challengeType: 0
videoUrl: 'https://scrimba.com/c/cg4dpt9'
forumTopicId: 301047
dashedName: create-a-gradual-css-linear-gradient
---

# --description--

Applying a color on HTML elements is not limited to one flat hue. CSS provides the ability to use color transitions, otherwise known as gradients, on elements. This is accessed through the `background` property's `linear-gradient()` function. Here is the general syntax:

```css
background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);
```

Das erste Argument gibt die Richtung an, von der der Farbübergang ausgeht. Sie kann in Grad angegeben werden, wobei `90deg` einen horizontalen Farbverlauf (von links nach rechts) und `45deg` einen diagonalen Farbverlauf (von links unten nach rechts oben) ergibt. Die folgenden Argumente geben die Reihenfolge der Farben an, die im Farbverlauf verwendet werden.

Beispiel:

```css
background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));
```

# --instructions--

Verwende für den `background` des `div`-Elements einen `linear-gradient()` und stelle ihn aus einer Richtung von 35 Grad, mit einer Farbänderung von `#CCFFFF` auf `#FFCCCC` ein.

# --hints--

Das `div`-Element sollte einen `linear-gradient` `background` mit der angegebenen Richtung bzw. den Farben haben.

```js
const divElement = document.querySelector('div');
const divStyle = window.getComputedStyle(divElement); 
assert.match(divStyle?.background, /linear-gradient\(35deg, rgb\(204, 255, 255\), rgb\(255, 204, 204\)\)/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  div {
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin: 50px auto;

  }

</style>

<div></div>
```

# --solutions--

```html
<style>
  div {
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin: 50px auto;
    background: linear-gradient(35deg, #CCFFFF, #FFCCCC);
  }
</style>
<div></div>
```
