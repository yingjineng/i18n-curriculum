---
id: 587d78a8367417b2b2512ae3
title: Elemente mithilfe einer unendlichen Anzahl von Animationsdurchläufen ununterbrochen animieren
challengeType: 0
videoUrl: 'https://scrimba.com/c/cVJDVfq'
forumTopicId: 301041
dashedName: animate-elements-continually-using-an-infinite-animation-count
---

# --description--

The previous challenges covered how to use some of the animation properties and the `@keyframes` rule. Another animation property is the `animation-iteration-count`, which allows you to control how many times you would like to loop through the animation. Hier ist ein Beispiel:

```css
animation-iteration-count: 3;
```

In diesem Fall stoppt die Animation nach drei Durchläufen, aber es ist möglich, die Animation kontinuierlich laufen zu lassen, indem der Wert auf `infinite` (dt. unendlich) gesetzt wird.

# --instructions--

Um den Ball auf der rechten Seite ununterbrochen springen zu lassen, ändere die `animation-iteration-count`-Eigenschaft auf `infinite`.

# --hints--

Die Eigenschaft `animation-iteration-count` sollte einen Wert von `infinite` haben.

```js
const ballElement = document.querySelector('#ball');
const ballStyle = window.getComputedStyle(ballElement); 
assert.equal(ballStyle?.animationIterationCount, 'infinite');
```

# --seed--

## --seed-contents--

```html
<style>

  #ball {
    width: 100px;
    height: 100px;
    margin: 50px auto;
    position: relative;
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    animation-name: bounce;
    animation-duration: 1s;
    animation-iteration-count: 3;
  }

  @keyframes bounce{
    0% {
      top: 0px;
    }
    50% {
      top: 249px;
      width: 130px;
      height: 70px;
    }
    100% {
      top: 0px;
    }
  }
</style>
<div id="ball"></div>
```

# --solutions--

```html
<style>
  #ball {
    width: 100px;
    height: 100px;
    margin: 50px auto;
    position: relative;
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    animation-name: bounce;
    animation-duration: 1s;
    animation-iteration-count: infinite;
  }

  @keyframes bounce{
    0% {
      top: 0px;
    }
    50% {
      top: 249px;
      width: 130px;
      height: 70px;
    }
    100% {
      top: 0px;
    }
  }
</style>
<div id="ball"></div>
```
