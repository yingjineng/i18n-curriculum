---
id: 587d7fa7367417b2b2512bc4
title: Працюйте з даними в D3
challengeType: 6
forumTopicId: 301497
dashedName: work-with-data-in-d3
---

# --description--

The D3 library focuses on a data-driven approach. When you have a set of data, you can apply D3 methods to display it on the page. Data comes in many formats, but this challenge uses a simple array of numbers.

Перший крок: повідомити D3 про дані. Метод `data()` використовують до виділених елементів DOM, щоб приєднати дані до цих елементів. Набір даних передається як аргумент до методу.

Поширений шаблон робочого процесу — це створити новий елемент в документі для кожної частини даних у наборі. D3 має метод `enter()` для цієї мети.

Коли метод `enter()` об’єднується з методом `data()`, то він розглядає вибрані елементи зі сторінки та порівнює їх з кількістю елементів даних у наборі. Якщо кількість елементів менша за кількість елементів даних, то він створює відсутні елементи.

Ось приклад, який вибирає елемент `ul` та створює новий елемент списку, що базується на кількості записів у масиві:

```html
<body>
  <ul></ul>
  <script>
    const dataset = ['a', 'b', 'c'];
    d3.select('ul')
      .selectAll('li')
      .data(dataset)
      .enter()
      .append('li')
      .text('New item');
  </script>
</body>
```

Вибір елементів, які ще не існують, може здатися вам складним. Цей код повідомляє D3, що спочатку на сторінці потрібно вибрати `ul`. Потім виберіть всі елементи списку, що поверне порожню вибірку. Після цього метод `data()` оглядає набір даних і тричі запускає наступний код, по одному разу для кожного елемента в масиві. Метод `enter()` бачить, що на сторінці немає елементів `li`, але йому потрібно 3 (по одному для кожної частини даних в `dataset`). Нові елементи `li` приєднуються до `ul` та мають текст `New item`.

# --instructions--

Оберіть вузол `body`, а потім оберіть всі елементи `h2`. Заставте D3 створити та приєднати тег `h2` до кожного елемента в масиві `dataset`. Текстом в `h2` має бути `New Title`. Код має використати методи `data()` та `enter()`.

# --hints--

Документ має містити 9 елементів `h2`.

```js
assert.lengthOf(document.querySelectorAll('h2'), 9);
```

Текстом в елементах `h2` має бути `New Title`. Великі літери та інтервали мають збігатися точно.

```js
const h2Elements = document.querySelectorAll('h2');
for (let i = 0; i < h2Elements.length; i++) {
  assert.match(h2Elements[i]?.textContent, /New Title/g);
}
```

Код має використати метод `data()`.

```js
assert.match(code, /\.data/g);
```

Код має використати метод `enter()`.

```js
assert.match(code, /\.enter/g);
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    // Add your code below this line



    // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const dataset = [12, 31, 22, 17, 25, 18, 29, 14, 9];

    d3.select('body')
      .selectAll('h2')
      .data(dataset)
      .enter()
      .append('h2')
      .text('New Title');
  </script>
</body>
```
