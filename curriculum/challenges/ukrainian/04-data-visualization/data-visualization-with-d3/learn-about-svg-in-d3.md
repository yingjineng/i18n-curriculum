---
id: 587d7fa8367417b2b2512bcb
title: Дізнайтесь про SVG в D3
challengeType: 6
forumTopicId: 301489
dashedName: learn-about-svg-in-d3
---

# --description--

<dfn>SVG</dfn> stands for <dfn>Scalable Vector Graphics</dfn>.

«Масштабована» означає, що якщо ви збільшите або зменшите об’єкт, то він не буде виглядати піксельним. Він масштабується за допомогою дисплейної системи, чи то маленький мобільний екран, чи то великий телевізійний монітор.

SVG використовують для того, щоб створити загальні геометричні фігури. Оскільки D3 відтворює дані у візуальному вигляді, то він використовує SVG для того, щоб створити фігури для візуалізації. Фігури SVG для вебсторінки мають знаходитись в тегу HTML `svg`.

CSS може бути масштабованим, якщо стилі використовують відносні одиниці (`vh`, `vw` або відсотки), але використання SVG гнучкіше для створення візуалізації даних.

# --instructions--

Додайте вузол `svg` до `body`, використовуючи `append()`. Надайте йому атрибут `width` зі значенням наданої константи `w` та атрибут `height` зі значенням наданої константи `h`, використовуючи метод `attr()` або `style()`. Ви побачите його в результаті, оскільки до нього застосовано рожевий `background-color` в тегу `style`.

**Примітка:** атрибути висоти та ширини не мають одиниць при використанні методу `attr()`. Це будівельний блок масштабування: елемент завжди матиме співвідношення ширини до висоти 5:1, незалежно від рівня масштабування.

# --hints--

Документ має містити 1 елемент `svg`.

```js
assert.lengthOf(document.querySelectorAll('svg'), 1);
```

Елемент `svg` повинен мати атрибут `width` зі значенням `500` або стилізований так, щоб значенням ширини було `500px`.

```js
const svg = document.querySelector('svg');
assert.exists(svg); 
const width = window.getComputedStyle(svg)['width'];
assert.isTrue(svg?.getAttribute('width') === '500' || width === '500px');
```

Елемент `svg` повинен мати атрибут `height` зі значенням `100` або стилізований так, щоб значенням висоти було `100px`.

```js
const svg = document.querySelector('svg');
assert.exists(svg); 
const height = window.getComputedStyle(svg)['height'];
assert.isTrue(svg?.getAttribute('height') === '100' || height === '100px');
```

# --seed--

## --seed-contents--

```html
<style>
  svg {
    background-color: pink;
  }
</style>
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    const w = 500;
    const h = 100;

    const svg = d3.select('body');
    // Add your code below this line



    // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<style>
  svg {
    background-color: pink;
  }
</style>
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    const w = 500;
    const h = 100;

    const svg = d3
      .select('body')
      .append('svg')
      .attr('width', w)
      .attr('height', h);
  </script>
</body>
```
