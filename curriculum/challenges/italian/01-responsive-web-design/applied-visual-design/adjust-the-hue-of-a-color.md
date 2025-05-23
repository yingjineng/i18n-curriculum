---
id: 587d78a4367417b2b2512ad4
title: Regolare la tonalità di un colore
challengeType: 0
videoUrl: 'https://scrimba.com/c/cPp38TZ'
forumTopicId: 301036
dashedName: adjust-the-hue-of-a-color
---

# --description--

Colors have several characteristics including hue, saturation, and lightness. CSS3 introduced the `hsl()` function as an alternative way to pick a color by directly stating these characteristics.

**Tonalità** è ciò che la gente generalmente intende come 'colore'. Se si immagina uno spettro di colori che inizia con il rosso a sinistra, passando attraverso il verde nel mezzo, e blu a destra, la tonalità è dove un colore si posiziona lungo questa linea. Con l'`hsl()`, la tonalità utilizza il concetto del cerchio cromatico invece dello spettro, dove l'angolo del colore sul cerchio è indicato come valore compreso tra 0 e 360.

**Saturazione** è la quantità di grigio in un colore. Un colore completamente saturo non ha grigio in esso, e un colore minimamente saturo è quasi completamente grigio. Questo dato è in percentuale, dove 100% la saturazione completa.

**Luminosità** è la quantità di bianco o nero in un colore. Viene data una percentuale che va dallo 0% (nero) al 100% (bianco), dove il 50% è il colore normale.

Ecco alcuni esempi di utilizzo dell'`hsl()` con colori di luminosità normali completamente saturati:

<table><thead><tr><th>Color</th><th>HSL</th></tr></thead><tbody><tr><td>red</td><td>hsl(0, 100%, 50%)</td></tr><tr><td>yellow</td><td>hsl(60, 100%, 50%)</td></tr><tr><td>green</td><td>hsl(120, 100%, 50%)</td></tr><tr><td>cyan</td><td>hsl(180, 100%, 50%)</td></tr><tr><td>blue</td><td>hsl(240, 100%, 50%)</td></tr><tr><td>magenta</td><td>hsl(300, 100%, 50%)</td></tr></tbody></table>

# --instructions--

Cambia il `background-color` di ogni elemento `div` basandoti sui nomi delle classi (`green` - verde, `cyan` - ciano o `blue` - blu) utilizzando la proprietà `hsl()`. Tutti e tre dovrebbero avere piena saturazione e luminosità normale.

# --hints--

Il codice dovrebbe avere la funzione `hsl()` per dichiarare il colore verde.

```js
assert.match(code,/\.green\s*?{\s*?background-color\s*:\s*?hsl/gi);
```

Il codice dovrebbe avere la funzione `hsl()` per dichiarare il colore ciano.

```js
assert.match(code,/\.cyan\s*?{\s*?background-color\s*:\s*?hsl/gi);
```

Il codice dovrebbe avere la funzione `hsl()` per dichiarare il colore blu.

```js
assert.match(code,/\.blue\s*?{\s*?background-color\s*:\s*?hsl/gi);
```

L'elemento `div` con classe `green` dovrebbe avere un `background-color` verde.

```js
const greenElement = document.querySelector(".green");
const greenStyle = window.getComputedStyle(greenElement); 
assert.equal(greenStyle?.backgroundColor, 'rgb(0, 255, 0)');
```

L'elemento `div` con classe `cyan` dovrebbe avere un `background-color` ciano.

```js
const cyanElement = document.querySelector(".cyan");
const cyanStyle = window.getComputedStyle(cyanElement); 
assert.equal(cyanStyle?.backgroundColor, 'rgb(0, 255, 255)');
```

L'elemento `div` con classe `blue` dovrebbe avere un `background-color` blu.

```js
const blueElement = document.querySelector(".blue");
const blueStyle = window.getComputedStyle(blueElement); 
assert.equal(blueStyle?.backgroundColor, 'rgb(0, 0, 255)');
```

# --seed--

## --seed-contents--

```html
<style>
  body {
    background-color: #FFFFFF;
  }

  .green {
    background-color: #000000;
  }

  .cyan {
    background-color: #000000;
  }

  .blue {
    background-color: #000000;
  }

  div {
    display: inline-block;
    height: 100px;
    width: 100px;
  }
</style>

<div class="green"></div>
<div class="cyan"></div>
<div class="blue"></div>
```

# --solutions--

```html
<style>
  body {
    background-color: #FFFFFF;
  }

  .green {
    background-color: hsl(120, 100%, 50%);
  }

  .cyan {
    background-color:   hsl(180, 100%, 50%);
  }

  .blue {
    background-color: hsl(240, 100%, 50%);
  }

  div {
    display: inline-block;
    height: 100px;
    width: 100px;
  }
</style>
<div class="green"></div>
<div class="cyan"></div>
<div class="blue"></div>
```
