---
id: 587d7fb0367417b2b2512bed
title: Знайомство з консоллю Node
challengeType: 2
forumTopicId: 301515
dashedName: meet-the-node-console
---

# --description--

Робота над цими завданнями передбачає написання коду за допомогою одного з наступних методів:

- Clone <a href="https://github.com/freeCodeCamp/boilerplate-express/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete these challenges locally.
- Використовуйте конструктор сайту на власний розсуд, щоб завершити проєкт. Переконайтеся, що ви зберегли всі файли з нашого репозиторію GitHub.

Під час процесу розробки важливо перевіряти, що відбувається у коді.

Node — це всього лиш середовище JavaScript. Як і клієнтська сторона JavaScript, ви можете використовувати консоль для показу корисної інформації щодо налагодження. На своїй локальній машині ви побачите вивід консолі в терміналі.

Ми рекомендуємо тримати термінал відкритим під час роботи над цими завданнями. Читаючи вивід в терміналі, ви можете побачити будь-які помилки, що можуть виникнути.

Після внесення змін до файлів потрібно перезапустити сервер.

Сервер можна зупинити в терміналі за допомогою `Ctrl + C` та запустити за допомогою безпосередньо Node (`node mainEntryFile.js`) або запустити скрипт в файлі `package.json` за допомогою `npm run`.

Наприклад, щоб запустити скрипт `"start": "node server.js"` в терміналі, використайте `npm run start`.

Щоб впровадити автоматичний перезапуск серверу під час зберігання файлів, Node надає прапорець `--watch`, який можна додати до початкового скрипту `"start": "node --watch server.js"`, або можна завантажити пакет npm (наприклад, `nodemon`). Це буде вашим завданням.

# --instructions--

Модифікуйте файл `myApp.js`, щоб на консолі було виведено "Hello World".

# --hints--

`"Hello World"` має бути на консолі

```js
  $.get(code + '/_api/hello-console').then(
    (data) => {
      assert.isTrue(data.passed, '"Hello World" is not in the server console');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

