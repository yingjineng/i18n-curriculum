---
id: 587d7fb0367417b2b2512bee
title: Запуск робочого серверу Express
challengeType: 2
forumTopicId: 301519
dashedName: start-a-working-express-server
---

# --description--

У перших двох рядках файлу `myApp.js` можна побачити, наскільки легко створити об’єкт Express. Цей об’єкт має декілька методів, і багато з них ви вивчите за допомогою цих завдань. Одним із фундаментальних методів є `app.listen(port)`. Він повідомляє вашому серверу прослуховувати певний порт, переводячи його в робочий стан. З міркувань тестування нам потрібно, щоб програма працювала у фоновому режимі, тому ми додали цей метод у файл `server.js`.

Давайте обслужимо наш перший рядок! Маршрути в Express мають таку структуру: `app.METHOD(PATH, HANDLER)`. METHOD — це метод http у нижньому регістрі. PATH — це відносний шлях на сервері (може бути рядком або навіть регулярним виразом). HANDLER — це функція, яку викликає Express при збігу маршруту. Обробники приймають форму `function(req, res) {...}`, де req — об’єкт запиту, а res — об’єкт відповіді. Наприклад, обробник

```js
function(req, res) {
  res.send('Response String');
}
```

буде обслуговувати рядок 'Response String'.

# --instructions--

Використайте метод `app.get()`, щоб обслужити рядок "Hello Express" для запитів GET, які відповідають (кореневому) шляху `/`. Be sure that your code works by looking at the logs.

**Примітка:** весь код для цих уроків потрібно додавати між рядками коду, з яких ми починали.

# --hints--

Застосунок має обслуговувати рядок 'Hello Express'

```js
  $.get(code).then(
    (data) => {
      assert.equal(
        data,
        'Hello Express',
        'Your app does not serve the text "Hello Express"'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

