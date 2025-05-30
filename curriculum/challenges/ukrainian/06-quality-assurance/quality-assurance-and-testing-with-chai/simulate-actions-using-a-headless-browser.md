---
id: 587d824f367417b2b2512c5c
title: Імітуйте дії за допомогою headless браузера
challengeType: 2
dashedName: simulate-actions-using-a-headless-browser
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

У наступних завданнях ви будете імітувати взаємодію людини зі сторінкою, використовуючи headless браузер.

Headless браузери — це веббраузери без графічного інтерфейсу користувача. Вони можуть візуалізувати та інтерпретувати HTML, CSS та JavaScript так само, як і звичайний браузер, що робить їх надзвичайно корисними для тестування вебсторінок.

Для вирішення наступних завдань ви будете використовувати Zombie.js — це легкий браузер без графічного інтерфейсу, який не покладається на встановлення додаткових двійкових файлів. Але існує і багато інших потужніших опцій headless браузера.

Mocha дозволяє вам запустити певний код перед виконанням самого тесту. Це може бути корисним для таких дій, як додавання записів до бази даних, які будуть використовуватися в решті тестів.

У headless браузері перед запуском тестів вам потрібно **відвідати** сторінку, яку ви тестуватимете.

Хук `suiteSetup` виконується лише один раз, на початку набору тестів.

Існують й інші типи хуків, які можуть виконувати код перед кожним тестом, після кожного тесту або в кінці набору тестів. Для детальної інформації перегляньте документацію Mocha.

# --instructions--

У межах `test/2_functional-tests.js` одразу після оголошення `Browser` додайте URL-адресу свого проєкту до властивості `site` змінної:

```js
Browser.site = 'http://0.0.0.0:3000'; // Your URL here
```

Потім на кореневому рівні набору `'Functional Tests with Zombie.js'` створіть новий екземпляр об’єкта `Browser` з наступним кодом:

```js
const browser = new Browser();
```

І використайте хук `suiteSetup`, щоб направити `browser` до маршруту `/` за допомогою коду нижче. **Примітка**: `done` передається як зворотний виклик до `browser.visit`, тому не викликайте його.

```js
suiteSetup(function(done) {
  return browser.visit('/', done);
});
```

# --hints--

Необхідно пройти всі тести.

```js
  $.get(code + '/_api/get-tests?type=functional&n=4').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

