---
id: bad87fee1348bd9aedf08721
title: Usar código hexadecimal para misturar cores
challengeType: 0
videoUrl: 'https://scrimba.com/c/cK89PhP'
forumTopicId: 18359
dashedName: use-hex-code-to-mix-colors
---

# --description--

To review, hex codes use 6 hexadecimal digits to represent colors, two each for red (R), green (G), and blue (B) components.

A partir dessas três cores puras (vermelho, verde e azul), podemos variar as quantidades de cada uma para criar mais de 16 milhões de outras cores!

Por exemplo, laranja é vermelho puro, misturado com um pouco de verde e sem azul. Em código hexadecimal, essa cor se traduz em `#FFA500`.

O dígito `0` é o número mais baixo em código hexadecimal e representa uma ausência completa de cor.

O dígito `F` é o número mais alto em código hexadecimal e representa o brilho máximo possível.

# --instructions--

Substitua as palavras que representam cores no elemento `style` por seus códigos hexadecimais corretos.

<table><tbody><tr><th>Color</th><th>Hex Code</th></tr><tr><td>Dodger Blue</td><td><code>#1E90FF</code></td></tr><tr><td>Green</td><td><code>#00FF00</code></td></tr><tr><td>Orange</td><td><code>#FFA500</code></td></tr><tr><td>Red</td><td><code>#FF0000</code></td></tr></tbody></table>

# --hints--

O elemento `h1` com o texto `I am red!` deve receber a propriedade `color` com o valor hexadecimal que representa a cor vermelha.

```js
const redText = document.querySelector('.red-text');
const color = window.getComputedStyle(redText)['color']; 
assert.strictEqual(color, 'rgb(255, 0, 0)');
```

O código hexadecimal (`hex code`) para a cor vermelha deve ser usado em vez da palavra `red`.

```js
assert.match(code, /\.red-text\s*?{\s*?color\s*:\s*?(#FF0000|#F00)\s*?;?\s*?}/gi);
```

O elemento `h1` com o texto `I am green!` deve receber a propriedade `color` com o valor hexadecimal que representa a cor verde.

```js
const greenText = document.querySelector('.green-text');
const color = window.getComputedStyle(greenText)['color']; 
assert.strictEqual(color, 'rgb(0, 255, 0)');
```

O código hexadecimal (`hex code`) para a cor verde deve ser usado em vez da palavra `green`.

```js
assert.match(code, /\.green-text\s*?{\s*?color\s*:\s*?(#00FF00|#0F0)\s*?;?\s*?}/gi);
```

O elemento `h1` com o texto `I am dodger blue!` deve receber a propriedade `color` com um valor de azul dodger.

```js
const blueText = document.querySelector('.dodger-blue-text');
const color = window.getComputedStyle(blueText)['color']; 
assert.strictEqual(color, 'rgb(30, 144, 255)');
```

O código hexadecimal (`hex code`) para a cor azul dodger deve ser usado em vez da palavra `dodgerblue`.

```js
assert.match(code, /\.dodger-blue-text\s*?{\s*?color\s*:\s*?#1E90FF\s*?;?\s*?}/gi);
```

O elemento `h1` com o texto `I am orange!` deve receber a propriedade `color` com um valor de laranja.

```js
const orangeText = document.querySelector('.orange-text');
const color = window.getComputedStyle(orangeText)['color']; 

assert.strictEqual(color, 'rgb(255, 165, 0)');
```

O código hexadecimal (`hex code`) para a cor laranja deve ser usado em vez da palavra `orange`.

```js
assert.match(code, /\.orange-text\s*?{\s*?color\s*:\s*?#FFA500\s*?;?\s*?}/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  .red-text {
    color: black;
  }
  .green-text {
    color: black;
  }
  .dodger-blue-text {
    color: black;
  }
  .orange-text {
    color: black;
  }
</style>

<h1 class="red-text">I am red!</h1>

<h1 class="green-text">I am green!</h1>

<h1 class="dodger-blue-text">I am dodger blue!</h1>

<h1 class="orange-text">I am orange!</h1>
```

# --solutions--

```html
<style>
  .red-text {
    color: #FF0000;
  }
  .green-text {
    color: #00FF00;
  }
  .dodger-blue-text {
    color: #1E90FF;
  }
  .orange-text {
    color: #FFA500;
  }
</style>

<h1 class="red-text">I am red!</h1>

<h1 class="green-text">I am green!</h1>

<h1 class="dodger-blue-text">I am dodger blue!</h1>

<h1 class="orange-text">I am orange!</h1>
```
