---
id: bad82fee1348bd9aedf08721
title: Mische Farben mit RGB
challengeType: 0
videoUrl: 'https://scrimba.com/c/cm24JU6'
forumTopicId: 18368
dashedName: use-rgb-to-mix-colors
---

# --description--

Just like with hex code, you can mix colors in RGB by using combinations of different values.

# --instructions--

Ersetze die Hex-Codes in unserem `style`-Element mit entsprechenden RGB-Werten.

<table><tbody><tr><th>Color</th><th>RGB</th></tr><tr><td>Blue</td><td><code>rgb(0, 0, 255)</code></td></tr><tr><td>Red</td><td><code>rgb(255, 0, 0)</code></td></tr><tr><td>Orchid</td><td><code>rgb(218, 112, 214)</code></td></tr><tr><td>Sienna</td><td><code>rgb(160, 82, 45)</code></td></tr></tbody></table>

# --hints--

Dein `h1`-Element mit dem Text `I am red!` sollte einen roten `color`-Wert besitzen.

```js
const redText = document.querySelector('.red-text');
const color = window.getComputedStyle(redText)['color']; 
assert.strictEqual(color, 'rgb(255, 0, 0)');
```

Du solltest `rgb` für die Farbe Rot verwenden.

```js
assert.match(code, /\.red-text\s*{\s*color\s*:\s*rgb\(\s*255\s*,\s*0\s*,\s*0\s*\)\s*;?\s*}/gi);
```

Dein `h1`-Element mit dem Text `I am orchid!` sollte einen `color`-Wert von Orchideen-Lila besitzen.

```js
const orchidText = document.querySelector('.orchid-text');
const color = window.getComputedStyle(orchidText)['color']; 
assert.strictEqual(color, 'rgb(218, 112, 214)');
```

Du solltest einen `rgb` Wert für die Farbe Orchidee verwenden.

```js
assert.match(__helpers.removeCssComments(code), /\.orchid-text\s*{\s*color\s*:\s*rgb\(\s*218\s*,\s*112\s*,\s*214\s*\)\s*;?\s*}/gi);
```

Dein `h1`-Element mit dem Text `I am blue!` sollte einen blauen `color`-Wert besitzen.

```js
const blueText = document.querySelector('.blue-text');
const color = window.getComputedStyle(blueText)['color']; 
assert.strictEqual(color, 'rgb(0, 0, 255)');
```

Du solltest `rgb` für die Farbe Blau verwenden.

```js
assert.match(__helpers.removeCssComments(code), /\.blue-text\s*{\s*color\s*:\s*rgb\(\s*0\s*,\s*0\s*,\s*255\s*\)\s*;?\s*}/gi);
```

Dein `h1` Element mit dem Text `I am sienna!` sollte einen `color` Wert von Siena Ocker haben.

```js
const siennaText = document.querySelector('.sienna-text');
const color = window.getComputedStyle(siennaText)['color']; 
assert.strictEqual(color, 'rgb(160, 82, 45)');
```

Du solltest einen `rgb`-Wert für die Farbe Siena Ocker verwenden.

```js
assert.match(__helpers.removeCssComments(code), /\.sienna-text\s*{\s*color\s*:\s*rgb\(\s*160\s*,\s*82\s*,\s*45\s*\)\s*;?\s*}/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  .red-text {
    color: #000000;
  }
  .orchid-text {
    color: #000000;
  }
  .sienna-text {
    color: #000000;
  }
  .blue-text {
    color: #000000;
  }
</style>

<h1 class="red-text">I am red!</h1>

<h1 class="orchid-text">I am orchid!</h1>

<h1 class="sienna-text">I am sienna!</h1>

<h1 class="blue-text">I am blue!</h1>
```

# --solutions--

```html
<style>
  .red-text {
    color: rgb(255, 0, 0);
  }
  .orchid-text {
    color: rgb(218, 112, 214);
  }
  .sienna-text {
    color: rgb(160, 82, 45);
  }
  .blue-text {
    color:rgb(0, 0, 255);
  }
</style>

<h1 class="red-text">I am red!</h1>

<h1 class="orchid-text">I am orchid!</h1>

<h1 class="sienna-text">I am sienna!</h1>

<h1 class="blue-text">I am blue!</h1>
```
