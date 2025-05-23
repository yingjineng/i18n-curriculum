---
id: 587d7fa6367417b2b2512bc2
title: Додайте елементи документа за допомогою D3
challengeType: 6
forumTopicId: 301474
dashedName: add-document-elements-with-d3
---

# --description--

D3 has several methods that let you add and change elements in your document.

Метод `select()` вибирає один елемент з документа. Він приймає аргумент для назви елемента та повертає вузол HTML для першого елемента в документі, який збігається з назвою. Ось приклад:

```js
const anchor = d3.select('a');
```

Приклад вище знаходить перший елемент посилання на сторінці та зберігає його вузол HTML в змінній `anchor`. Вибирати елементи можна і за допомогою інших методів. Частина `d3` в прикладі — це посилання на об’єкт D3, за допомогою якого ми отримуємо доступ до методів D3.

Ще два корисні методи: `append()` та `text()`.

Метод `append()` приймає аргумент для елементу, який ви хочете додати до документа. Він приєднує вузол HTML до вибраного елемента та повертає обробник цього вузла.

Метод `text()` або встановлює текст вибраного вузла, або отримує поточний текст. Щоб задати значення, потрібно передати рядок у вигляді аргументу в дужках методу.

Ось приклад, який вибирає невпорядкований список, додає елемент списку та додає текст:

```js
d3.select('ul')?.append('li').text('Very important item');
```

D3 дозволяє поєднувати методи за допомогою крапки, щоб виконувати декілька дій по черзі.

# --instructions--

Використайте метод `select`, щоб вибрати тег `body` в документі. Потім використайте метод `append`, щоб додати `h1` до нього та додайте текст `Learning D3` в елемент `h1`.

# --hints--

`body` повинен містити один елемент `h1`.

```js
const body = document.querySelector('body');
const headers = body?.querySelectorAll('h1');
assert.lengthOf(headers, 1);
```

Елемент `h1` повинен містити текст `Learning D3`.

```js
assert.strictEqual(document.querySelector('h1')?.textContent, 'Learning D3');
```

Код повинен отримати доступ до об’єкта `d3`.

```js
assert.match(code, /d3/g);
```

Код має використати метод `select`.

```js
assert.match(code, /\.select/g);
```

Код має використати метод `append`.

```js
assert.match(code, /\.append/g);
```

Код має використати метод `text`.

```js
assert.match(code, /\.text/g);
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    // Add your code below this line



    // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    d3.select('body').append('h1').text('Learning D3');
  </script>
</body>
```
