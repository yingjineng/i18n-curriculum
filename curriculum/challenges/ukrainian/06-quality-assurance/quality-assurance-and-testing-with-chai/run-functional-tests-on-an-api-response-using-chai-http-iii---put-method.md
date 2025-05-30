---
id: 587d824f367417b2b2512c5a
title: Запустіть функціональні тести на відповіді API за допомогою методу Chai-HTTP III - PUT
challengeType: 2
forumTopicId: 301590
dashedName: run-functional-tests-on-an-api-response-using-chai-http-iii---put-method
---

# --description--

As a reminder, this project is being built upon the following starter project  cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Під час тесту запиту `PUT` ви часто будете надсилати й дані. Дані, які поміщені у вашому запиті `PUT`, називаються тілом запиту.

Щоб відправити запит `PUT` та об’єкт JSON до `'/travellers'`, ви можете використати методи `put` та `send` плагіну `chai-http`:

```js
chai
  .request(server)
  .keepOpen()
  .put('/travellers')
  .send({
    "surname": [last name of a traveller of the past]
  })
  ...
```

Відповідь маршруту:

```json
{
  "name": [first name],
  "surname": [last name],
  "dates": [birth - death years]
}
```

Перегляньте код сервера для різних відповідей на кінцевій точці `'/travellers'`.

# --instructions--

У межах `tests/2_functional-tests.js` змініть `'Send {surname: "Colombo"}'` тесту (`// #3`) і використайте методи `put` та `send`, щоб перевірити кінцеву точку `'/travellers'`.

Надішліть наступний об’єкт JSON зі своїм запитом PUT:

```json
{
  "surname": "Colombo"
}
```

Перевірте наступне у межах зворотнього виклику `request.end`:

1.  The `status` should be `200`
2.  `type` має бути `application/json`
3.  `body.name` має бути `Cristoforo`
4.  `body.surname` має бути `Colombo`

Дотримуйтесь порядку тверджень вище, оскільки ми залежимо від нього. Не забудьте видалити `assert.fail()` після завершення.

# --hints--

Всі тести повинні бути успішно пройдені.

```js
  $.get(code + '/_api/get-tests?type=functional&n=2').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні перевірити, чи `res.status` має значення 200.

```js
  $.get(code + '/_api/get-tests?type=functional&n=2').then(
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

Ви повинні перевірити, чи `res.type` має значення `'application/json'`.

```js
  $.get(code + '/_api/get-tests?type=functional&n=2').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.type');
      assert.match(data.assertions[1].args[1], /('|")application\/json\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні перевірити, чи `res.body.name` має значення `'Cristoforo'`.

```js
  $.get(code + '/_api/get-tests?type=functional&n=2').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'equal');
      assert.equal(data.assertions[2].args[0], 'res.body.name');
      assert.match(data.assertions[2].args[1], /('|")Cristoforo\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні перевірити, чи `res.body.surname` має значення `'Colombo'`.

```js
  $.get(code + '/_api/get-tests?type=functional&n=2').then(
    (data) => {
      assert.equal(data.assertions[3].method, 'equal');
      assert.equal(data.assertions[3].args[0], 'res.body.surname');
      assert.match(data.assertions[3].args[1], /('|")Colombo\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

