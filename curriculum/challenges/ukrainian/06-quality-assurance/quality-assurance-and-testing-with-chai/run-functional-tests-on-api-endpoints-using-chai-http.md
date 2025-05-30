---
id: 587d824e367417b2b2512c58
title: Запустіть функціональні тести на кінцевих точках API за допомогою Chai-HTTP
challengeType: 2
forumTopicId: 301593
dashedName: run-functional-tests-on-api-endpoints-using-chai-http
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Mocha дозволяє перевіряти асинхронні операції (наприклад, виклики в кінцевих точках API) за допомогою плагіну `chai-http`.

Знизу наведено приклад тесту, який використовує `chai-http` для набору під назвою `'GET /hello?name=[name] => "hello [name]"'`:

```js
suite('GET /hello?name=[name] => "hello [name]"', function () {
  test('?name=John', function (done) {
    chai
      .request(server)
      .keepOpen()
      .get('/hello?name=John')
      .end(function (err, res) {
        assert.equal(res.status, 200, 'Response status should be 200');
        assert.equal(res.text, 'hello John', 'Response should be "hello John"');
        done();
      });
  });
});
```

Тест надсилає запит `GET` до сервера з назвою як рядок запиту URL (`?name=John`). У функії зворотного виклику методу `end` отримується об’єкт-відповідь (`res`), який містить властивість `status`.

Перший `assert.equal` перевіряє, чи статус дорівнює `200`. Другий `assert.equal` перевіряє, чи рядок відповіді (`res.text`) дорівнює `"hello John"`.

Зверніть увагу на параметр `done` у функції тесту зворотного виклику. Його необхідно викликати без аргументу в кінці тесту, щоб повідомити, що асинхронна операція завершена.

Наприкінці, зверніть увагу на метод `keepOpen` одразу після методу `request`. Зазвичай ви запускаєте свої тести з командного рядка або як частину автоматизованого процесу інтеграції, і ви можете дозволити `chai-http` запускати та зупиняти ваш сервер автоматично.

Однак тести, які виконуються, коли ви надсилаєте посилання на свій проєкт, вимагають, щоб сервер був запущений, тому вам потрібно використати метод `keepOpen`, щоб `chai-http` не зупинив сервер.

# --instructions--

У межах `tests/2_functional-tests.js` змініть `'Test GET /hello with no name'` тесту (`// #1`) для підтвердження `status` та `text`, щоб пройти тест. Не змінюйте аргументи, передані до тверджень.

Запити URL повинні бути відсутніми. Якщо немає назви запиту URL, то кінцева точка відповідає `hello Guest`.

# --hints--

Всі тести повинні бути успішно пройдені

```js
  $.get(code + '/_api/get-tests?type=functional&n=0').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні перевірити, чи `res.status` == 200

```js
  $.get(code + '/_api/get-tests?type=functional&n=0').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'equal');
      assert.equal(data.assertions[0].args[0], 'res.status');
      assert.equal(data.assertions[0].args[1], '200');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні перевірити, чи `res.text` == `'hello Guest'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=0').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.text');
      assert.match(data.assertions[1].args[1], /('|")hello Guest\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

