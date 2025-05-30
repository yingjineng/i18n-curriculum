---
id: 5895f70bf9fc0f352b528e64
title: Використання можливостей шаблонізатора
challengeType: 2
forumTopicId: 301567
dashedName: use-a-template-engines-powers
---

# --description--

One of the greatest features of using a template engine is being able to pass variables from the server to the template file before rendering it to HTML.

У своєму файлі Pug ви можете використовувати змінну, посилаючись на ім’я змінної як `#{variable_name}` в рядку з іншим текстом в елементі або використовуючи знак рівності в елементі без пробілу, наприклад, `p=variable_name`, що присвоює значення змінної до тексту елемента p.

Pug націлений на використання прогалин і вкладок для зображення вкладених елементів та скорочення обсягу коду, необхідного для створення красивого сайту.

Візьмемо, наприклад, такий код Pug:

```pug
head
  script(type='text/javascript').
    if (foo) bar(1 + 5);
body
  if youAreUsingPug
      p You are amazing
    else
      p Get on it!
```

Наведене вище видає наступний HTML:

```html
<head>
  <script type="text/javascript">
    if (foo) bar(1 + 5);
  </script>
</head>
<body>
  <p>You are amazing</p>
</body>
```

Ваш файл `index.pug`, поміщений у проєкті, використовує змінні `title` та `message`.

Передайте їх зі свого сервера до файлу Pug, додавши об’єкт як другий аргумент до свого виклику `res.render` зі змінними та їхніми значеннями. Надайте `title` значення `Hello`, а `message` значення `Please log in`.

Це має виглядати так:

```javascript
res.render('index', { title: 'Hello', message: 'Please log in' });
```

Тепер оновіть свою сторінку, і ви повинні побачити ці значення у перегляді в правильному місці, як зазначено у вашому файлі `index.pug`!

Відправте свою сторінку коли впевнились, що все правильно. Якщо виникають помилки, ви можете <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#use-a-template-engines-power-2" target="_blank" rel="noopener noreferrer nofollow">переглянути проєкт, виконаний до цього етапу</a>.

# --hints--

Pug повинен правильно відображати змінні.

```js
async () => {
  const url = new URL("/", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /pug-variable("|')>Please log in/gi,
    'Your projects home page should now be rendered by pug with the projects .pug file unaltered'
  );
}
```

