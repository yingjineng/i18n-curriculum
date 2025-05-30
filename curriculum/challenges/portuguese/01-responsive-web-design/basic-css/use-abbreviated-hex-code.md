---
id: bad87fee1348bd9aedf08719
title: Usar códigos hexadecimais de modo abreviado
challengeType: 0
videoUrl: 'https://scrimba.com/c/cRkpKAm'
forumTopicId: 18338
dashedName: use-abbreviated-hex-code
---

# --description--

Many people feel overwhelmed by the possibilities of more than 16 million colors. And it's difficult to remember hex code. Fortunately, you can shorten it.

Por exemplo, o código hexadecimal para vermelho `#FF0000` pode ser reduzido para `#F00`. Esta forma abreviada fornece um dígito para vermelho, um dígito para verde e um dígito para azul.

Isso reduz o número total de cores possíveis para cerca de 4.000. Mas os navegadores interpretarão tanto `#FF0000` quanto `#F00` como sendo exatamente a mesma cor.

# --instructions--

Tente usar os códigos hexadecimais abreviados para colorir os elementos corretos.

<table><tbody><tr><th>Color</th><th>Short Hex Code</th></tr><tr><td>Cyan</td><td><code>#0FF</code></td></tr><tr><td>Green</td><td><code>#0F0</code></td></tr><tr><td>Red</td><td><code>#F00</code></td></tr><tr><td>Fuchsia</td><td><code>#F0F</code></td></tr></tbody></table>

# --hints--

O elemento `h1` com o texto `I am red!` deve receber a propriedade `color` com o valor hexadecimal que representa a cor vermelha.

```js
const redText = document.querySelector('.red-text');
const color = window.getComputedStyle(redText)['color']; 
assert.strictEqual(color, 'rgb(255, 0, 0)');
```

O código hexadecimal (hex code) abreviado que representa a cor vermelha deve ser usado em vez do código hexadecimal `#FF0000`.

```js
assert.match(code,/\.red-text\s*?{\s*?color\s*:\s*?#F00\s*?;?\s*?}/gi);
```

O elemento `h1` com o texto `I am green!` deve receber a propriedade `color` com o valor hexadecimal que representa a cor verde.

```js
const greenText = document.querySelector('.green-text');
const color = window.getComputedStyle(greenText)['color']; 
assert.strictEqual(color, 'rgb(0, 255, 0)');
```

O código hexadecimal (hex code) abreviado que representa a cor verde deve ser usado em vez do código hexadecimal `#00FF00`.

```js
assert.match(__helpers.removeCssComments(code), /\.green-text\s*?{\s*?color\s*:\s*?#0F0\s*?;?\s*?}/gi);
```

O elemento `h1` com o texto `I am cyan!` deve receber a propriedade `color` com o valor hexadecimal que representa a cor ciano.

```js
const cyanText = document.querySelector('.cyan-text');
const color = window.getComputedStyle(cyanText)['color']; 
assert.strictEqual(color, 'rgb(0, 255, 255)');
```

O código hexadecimal (hex code) abreviado que representa a cor ciano deve ser usado em vez do código hexadecimal `#00FFFF`.

```js
assert.match(__helpers.removeCssComments(code), /\.cyan-text\s*?{\s*?color\s*:\s*?#0FF\s*?;?\s*?}/gi);
```

O elemento `h1` com o texto `I am fuchsia!` deve receber a propriedade `color` com o valor hexadecimal que representa a cor fúcsia.

```js
const fuchsiaText = document.querySelector('.fuchsia-text');
const color = window.getComputedStyle(fuchsiaText)['color']; 
assert.strictEqual(color,'rgb(255, 0, 255)');
```

O código hexadecimal (hex code) abreviado que representa a cor fúcsia deve ser usado em vez do código hexadecimal `#FF00FF`.

```js
assert.match(__helpers.removeCssComments(code), /\.fuchsia-text\s*?{\s*?color\s*:\s*?#F0F\s*?;?\s*?}/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  .red-text {
    color: #000000;
  }
  .fuchsia-text {
    color: #000000;
  }
  .cyan-text {
    color: #000000;
  }
  .green-text {
    color: #000000;
  }
</style>

<h1 class="red-text">I am red!</h1>

<h1 class="fuchsia-text">I am fuchsia!</h1>

<h1 class="cyan-text">I am cyan!</h1>

<h1 class="green-text">I am green!</h1>
```

# --solutions--

```html
<style>
  .red-text {
    color: #F00;
  }
  .fuchsia-text {
    color: #F0F;
  }
  .cyan-text {
    color: #0FF;
  }
  .green-text {
    color: #0F0;
  }
</style>

<h1 class="red-text">I am red!</h1>

<h1 class="fuchsia-text">I am fuchsia!</h1>

<h1 class="cyan-text">I am cyan!</h1>

<h1 class="green-text">I am green!</h1>
```
